---
title: World Locking Tools architecture
description: An introduction to the architecture underlying the World Locking Tools.
author: AMollis
ms.author: amollis
ms.date: 10/06/2021
ms.service: mixed-reality
ms.localizationpriority: high
ms.topic: concept-article
keywords: Unity, HoloLens, HoloLens 2, Augmented Reality, Mixed Reality, ARCore, ARKit, development, MRTK
---

# Architecture

The World Locking Tools for Unity architecture <span class="x x-first x-last">can</span> be summarized by the following diagram.

![Architectural diagram](~/Images/Architecture.png)

In general, the client application will make its intent known declaratively through settings on the World Locking Manager.

The managers, in turn, imperatively drive the processing by lower layers.

While all World Locking Tools capabilities are available through asset creation in the Unity Editor, every effort has been made to provide equal access to construction and configuration from script. Any capability available in Unity's Inspector but not from the scripting API should be considered a code defect. Reporting <span class="x x-first x-last">it</span> as a bug is appreciated! See [contributing](~/Documentation/HowTos/Contributing.md) for more info.

An exception to this flow is in the attachment point mechanism, which is discussed in detail in several articles within this documentation. In short, the client requests attachment points from the World Locking Attachment Point Manager. These attachment points then serve as conduits through which the application may be informed about refit operations.

## See also

* [Attachment points](~/Documentation/Concepts/Advanced/AttachmentPoints.md)
* [WorldLockingManager](Managers/WorldLockingManager.md)
* [IAnchorManager](Managers/IAnchorManager.md)
* [IFragmentManager](Managers/IFragmentManager.md)
* [IAttachmentPointManager](Managers/IAttachmentPointManager.md)
* [IAlignmentManager](Managers/IAlignmentManager.md)

And in API reference:

* [WorldLockingManager](xref:Microsoft.MixedReality.WorldLocking.Core.WorldLockingManager)
* [IAnchorManager](xref:Microsoft.MixedReality.WorldLocking.Core.IAnchorManager)
* [IFragmentManager](xref:Microsoft.MixedReality.WorldLocking.Core.IFragmentManager)
* [IAttachmentPointManager](xref:Microsoft.MixedReality.WorldLocking.Core.IAttachmentPointManager)
* [IAlignmentManager](xref:Microsoft.MixedReality.WorldLocking.Core.IAlignmentManager)