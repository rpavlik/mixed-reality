---
title: Fragments in World Locking Tools
description: Handling separate regions of tracker space which are unaware of each other.
author: AMollis
ms.author: amollis
ms.date: 10/06/2021
ms.service: mixed-reality
ms.localizationpriority: high
ms.topic: concept-article
keywords: Unity, HoloLens, HoloLens 2, Augmented Reality, Mixed Reality, ARCore, ARKit, development, MRTK
---

# Fragments

As mentioned, in World Locking Tools terminology, a *fragment* is a collection of things that exist in known relation with each other in the same coordinate space. However, there is generally no meaningful spatial relationship between different fragments.

A simple example might help clarify.

Imagine two well-lit rooms connected by a long dark hallway. The head-tracked session begins in the first room. The room is well-lit and has appropriate furnishings, and the user quickly and easily scans and maps it. Objects in the room, as well as any anchors created, are all in known positions relative to the head and relative to each other.

Since the second room hasn't even been visited yet, there's still no knowledge about its contents.

Now the user proceeds into the dark hallway. There, tracking is lost immediately because of the poor lighting. The user passes through the hallway to the second room.

In the second room, tracking is again restored and the user quickly scans the room, adding some anchors for good measure.

At this time, both rooms have been scanned, and the contents of each room is known relative to the other contents within the same room, but there's no knowledge about one room relative to the other. The hallway could've been of any length, and it may have curved.

These two rooms, then, are forming isolated islands of spatial relationship. We can view the group of interrelated objects in each room as "fragments". And in our hypothetical situation, our session now contains two fragments: one for each room. Because no tracking data was acquired in the hallway, there 's no corresponding hallway fragment.

All of the objects in both rooms have coordinates, but the two coordinate systems are unrelated. When the camera is in the second room, the head is placed in the same coordinate system as all the other objects in the second room. This allows those second room objects to be rendered appropriately relative to the user's perspective.

However, the objects in the first room are in an unrelated coordinate system. Depending on the length of the unmapped hallway, they might be meters or tens of meters away, or off to the side if the hallway bends. Therefore, without further information connecting the two spaces, the system doesn't have enough information to meaningfully place the first room's objects in the user's view. But the system does know it lacks sufficient information to render those objects correctly, and through the [attachment point](AttachmentPoints.md) mechanism it can inform the application of that condition.

## See also

* [Attachment points](AttachmentPoints.md)
* [Refit operations](RefitOperations.md)