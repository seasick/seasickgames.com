---
toc: true
layout: post
categories: [Unity]
title: Unity and simple waypoints
---

Unity again! Yesterday I tried to make my player gameObject to follow specific waypoints. I have published the code at GitHub. [Get it](https://github.com/seasick/Waypointer "Waypointer") and [Do What The Fuck You Want](http://sam.zoy.org/wtfpl/ "Do What The Fuck You Want Licence") with it. I always wanted to release code under this license. Finally ^^

Code explained
--------------

It isn't much code, so it is easily explained. The UnityScript file contains two classes. First we will have a look at the Waypointer.

The Waypointer class has two public attributes

-   speed ... The speed with which you gameObject will move
-   scale ... The scale of the waypoint hitbox. It is needed to tell if your gameObject reached a waypoint

As you can see, the class also has a private attribute - *queue. *It will contain a Queue object. This object is basically a "First In First Out" list. We can add waypoints on top of the stack, and remove them from the beginning if your gameObject reaches a waypoint. Since this Queue object isn't imported in Unity by default, we need to do this our self.

In the Update function we are doing only one thing: Get to the first waypoint in the queue. Ok, it is a little bit more. We have to check if there is a waypoint, and we need to look into the direction of the waypoint. Here you have the chance to improve the performance of the script. It isn't necessary to set the rotation of your gameObject everytime - we could set it once we remove a waypoint (given that there is another waypoint in the queue).

There is also a function for adding new waypoints. As you can see, this function isn't called anywhere. You have to call this function when you want to add a new waypoint. That way you could use this UnityScript not only for your player gameObject - you could use it on any gameObject you like. Think about several selected soldiers ... Of course your collision detection between them has to be way smarter - atm there is none ^^

I called this method from another component. With this component I can click anywhere onto the screen, and a new waypoint is added. Have some code ...

```csharp
#pragma strict

function Update
{
  // Check if a new Waypoint should be added
  if(Input.GetKeyDown(KeyCode.Mouse0)) {
    var playerPlane = new Plane(Vector3.up, transform.position);
    var ray = Camera.main.ScreenPointToRay (Input.mousePosition);
    var hitdist = 0.0;

    if (playerPlane.Raycast (ray, hitdist)) {
      var targetPoint = ray.GetPoint(hitdist);
      gameObject.GetComponent(Waypointer).AddWaypoint(ray.GetPoint(hitdist));
    }
  }
}
```

This AddWaypoint function will create a new gameObject with a BoxCollider. The public attribute scale will be assigned to the scale of the colliders transform. Also we will set the position and mark the collider as trigger. This way your gameObject won't bounce of it. After that we just enqueue the collider.

One important thing: We are also attaching the second class of this script to the collider. The Waypoint class. This class only has a OnTriggerEnter function which will check if the colliding object (normally your gameObject) has a Waypointer component on it. If so, it will use this component to tell it, that your gameObject has hit a waypoint.

And we are back in the Waypointer class. When your gameObject hit a waypoint, we just check if it is the first element in our queue. If so, we will remove it from the queue. Your gameObject will move on to the next waypoint.

Downsides
---------

At the moment there are a few downsides to this approach:

-   It is possible that this isn't working on your iPhone. I didn't bothered confirmed it yet, but Unity on the iPhone is only supported to a specific .NET compatibility level. Anyway - this has been a great opportunity to get into the .NET classes.
-   It will only work on plane terrain - or at least it will look odd on bumpy terrain.

Improvements?
-------------

There is enough space for improvements.

-   You could add a default prefab which will be used instead of the default collider. This way you could place something visible (and good looking) onto your screen.
-   As mentioned before - you could tweak the performance a little bit.
-   Add the ability to remove waypoints. Have a look at the [Queue](http://msdn.microsoft.com/en-us/library/7977ey2c.aspx ".NET Queue class") or implement your own FIFO list in pure UnityScript.

Unity and Mono/.NET compatibility level
---------------------------------------

Unity uses mono for all its magic. You can even import some .NET classes and use them in your scripts. It doesn't matter if you are using UnityScript, Boo or C#.

I haven't got into this topic very far, but you can set the API Compatibility Level in your projects settings (in Unity 3.5 you will find it in Player Settings > Other Settings). For me there are currently two entries

-   .NET 2.0
-   .NET 2.0 Subset

You can see on [this page](http://docs.unity3d.com/Documentation/ScriptReference/MonoCompatibility.html "Mono Compatibility Levels") which features are supported in which level.
