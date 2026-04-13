# Unity Design - Week 09

## Agenda

1. [Meta Quest SDK Building Blocks - Grab & Poke](#Grab-and-Poke-Interactions) 
2. [Meta Quest SDK - UI Set](#UI-Set)  
3. [XR Interaction Toolkit - Hand Tracking Examples](#XRI-Hand-Examples)

---

## Meta Quest Building Blocks – Hand Tracking: Grab & Poke Interactions

Meta’s **Building Blocks** provide a modular, plug-and-play approach for enabling intuitive **hand-tracking interactions** in VR. The two foundational VR interactions:

* **Grab** — picking up and manipulating virtual objects
* **Poke** — activating surfaces, buttons, and UI using direct fingertip contact
* https://developers.meta.com/horizon/documentation/unity/bb-overview/

---

## VR Core Interaction

### ✋ Hand Tracking Support

* Fully supports controller-free hand tracking
* Automatically handles pinch detection, collision volumes, and gesture recognition
* Requires no scripting to start interacting with Grab or Poke objects

### 🤏 Grab Interactions

Using the **Grabbable** Building Block, hand tracking enables:

* Natural pinch-to-grab gestures
* One-handed or two-handed grabbing
* Physics-based or kinematic movement
* Optional constraints (snap positions, rotation limits, movement smoothing)
* https://developers.meta.com/horizon/documentation/unity/unity-isdk-hand-grab-interaction

### 👉 Poke Interactions

Using **Poke Button** or **Poke Surface** Building Blocks, users can:

* Interact with 3D buttons, surfaces, toggles, and UI panels
* Trigger events when crossing an activation threshold
* Use fingertip-driven activation with accurate collision detection
* Get optional haptics, sounds, or animation feedback
* https://developers.meta.com/horizon/documentation/unity/unity-isdk-poke-interaction

---

## Adding Custom Hand Poses

Hand poses enhance the realism and comfort of hand-tracked interactions.

### Why Use Hand Poses?

* More natural grip around tools or objects
* Improved user comfort for repetitive grabs
* Better control over hand shape during interactions

### How to Add a Hand Pose (Building Blocks)

1. Select a **Grabbable** object.
2. Add a **Hand Pose** component from the Meta XR SDK (if not already included).
3. Enter **Hand Pose Recording Mode**:

   * Place your virtual hand around the object
   * Press **Record Pose**
4. Save left-hand and right-hand variants
5. Assign the poses to the object’s **Grab Pose Provider**

### Supported Pose Options

* **Static Poses** (snap to a fixed recorded shape)
* **Blended Hand Poses** (smooth interpolation during grab)
* **Mirrored or symmetric poses**
* **Pose-dependent grab points**

The Building Blocks system will automatically handle:

* Blending from open hand → grip → release
* Tracking your actual hand while shaping for the interactable

---

## UI Set 

The **UI Set** in the Meta Quest Interaction SDK provides a ready-to-use collection of prefabs, systems, and interaction components for creating VR-friendly user interfaces. These UI tools unify ray, poke, and grab-based interaction, enabling consistent UI behavior across hands and controllers.

The UI Set is ideal for dashboards, menus, panels, buttons, sliders, and any interactive UI surface within a VR environment.

* UI Set Elements
* https://developers.meta.com/horizon/documentation/unity/unity-isdk-uiset/

---

## 🎚 VR-Ready UI Controls

The UI Set provides VR-adapted versions of common UI elements:

* Buttons
* Sliders
* Toggles
* Scrollable panels
* Radial menus
* Surface-based interaction zones

These elements are optimized for hand proximity, poke depth, pointer accuracy, and VR ergonomics.

* Creating UI Panel with UI Set
* https://developers.meta.com/horizon/documentation/unity/unity-isdk-create-uiset-ui
* Using Unity Canvas UI Pokeable Elements
* https://developers.meta.com/horizon/documentation/unity/unity-isdk-create-pokeable-ui

---

## Components Included in the UI Set

### **1. Interactable UI Buttons**

* Poke and ray compatible
* Built-in press animation and feedback events
* Works out-of-the-box with Unity Events

### **2. VR Sliders and Value Controls**

* Supports drag via ray or direct grab
* Smooth motion with configurable sensitivity and snapping

### **3. Canvas + Event Systems (SDK Enhanced)**

* Custom Input Modules for Interaction SDK
* Replaces Unity’s standard event system to support hand/ray pointers
* Optimized for world-space UI canvases

### **4. Visual & Haptic Feedback**

* Hover and press states
* Animated transitions
* Optional haptics for controllers

---

## Microgestures Locomotion

Microgestures are refined thumb swipes and taps on the side of the index finger, allowing for intuitive, low-fatigue D-pad–style input without the need for traditional controllers. By integrating this feature, developers can offer users a more natural way to move and turn in VR, using just their hands. 
Microgestures unlock a new paradigm for hand-tracked interaction on Meta devices. Rather than relying on large hand motions or physical controllers, users can perform teleportation by tapping and rotate by swiping their thumb. This “tap-to-teleport, swipe-to-turn” input scheme aligns with familiar, spatially compact interface styles and reduces motion fatigue. 
Additionally, by decoupling movement logic via locomotion events, the system maintains clean architecture: gesture detection emits events, and locomotor components respond to them to perform movement. 

* https://developers.meta.com/horizon/documentation/unity/unity-isdk-locomotion-microgestures/
* Create Hotspot Locomotion Interactions
* https://developers.meta.com/horizon/documentation/unity/unity-isdk-create-locomotion-interactions

---

## Unity XR Interaction Toolkit 

* The **XR Interaction Toolkit** is a high-level, component-based system for building VR and AR interactions in Unity. 
* It provides core building blocks:

  * **Interactor** components (e.g., ray, direct)
  * **Interactable** components (objects you can grab, select, poke)
  * An **Interaction Manager** that connects Interactors and Interactables. ([Unity User Manual][1])
* It supports:

  * Cross-platform XR input (Meta Quest, OpenXR, etc.) ([Unity User Manual][1])
  * Hover, select, grab, and UI interactions
  * Haptics for XR controllers
  * Visual feedback like line renderers and hover tints
  * UI interaction via XR-compatible canvases (world-space) ([Unity User Manual][1])
* Includes utility systems, e.g., locomotion (teleport/move) and visuals. ([Unity User Manual][1])
* It integrates with Unity’s **Input System**, and depends on other packages:

---

## Hands Interaction Demo (XR Interaction Toolkit)

The **Hands Interaction Demo** is a sample scene provided with the toolkit that demonstrates how to use **hand tracking** (via the XR Hands package) to interact with objects and UI. 

* https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/samples-hands-interaction-demo.html
