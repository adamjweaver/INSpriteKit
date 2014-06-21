# INSpriteKit

[![CocoaDocs](http://cocoapod-badges.herokuapp.com/v/INSpriteKit/badge.png)](http://cocoadocs.org/docsets/INSpriteKit)

INSpriteKit adds some functionality to use with Sprite Kit.
This library is designed prior for iOS, but may also be used with OS X. In the later case mouse events are interpreted as touches.

The library consists of

### Math functions
- Different vector calculation methods for CGPoint and methods to convert.
- Methods for scalars like ScalarNearOther() to determine if a CGFloat is the same as another plus minus epsilon.
- Angular convertions and calculations.

### INSKScrollNode: A UIScrollView adaption for Sprite Kit
- Has full support for scrolling a content node into all directions.
- The scroll out behavior can be chosen from different presets.
- Paging is also supported.

### INSKButtonNode: A UIButton adaption for Sprite Kit
- Has full support for touch and state handling.
- Set different visual representations for the states disabled, normal, highlighted, selected and selected+highlighted.
- Get called back when the button is being pressed, released and released inside of its frame or use a delegate to get informed.

### INSKView: A SKView replacement for a better touch delivery
- Replaces Sprite Kit's touch delivery system with its own to workaround some touch detection bugs in Sprite Kit:
  - Respect a SKNode's `userInteractionEnabled` property.
  - Use a sprite node's frame instead of an extended bounding box with all children inside.
  - Use the visual representation of a sprite node even when rotated and not the extended frame.
- SKNodes may use `touchPriority` to get touches even when not on top of all other nodes.
- Add global touch observing nodes which get informed about touch events regardless of their position and visibility state. Nodes may also get touches this way even when not on the scene tree.
- Support the right mouse button in a Sprite Kit scene on OS X per default with the option to use AppKit's default behavior for context menus.

### A tiled image node for huge sprites
- INSKTiledImageNode can present images which are otherwise too huge for being used as a texture.
- Present images which are greater than 1024x1024 (respectively 2048x2048).

### Some categories
- SKNode: `bringToFront` and `sendToBack` for manipulating the tree order.
- SKNode: `changeParent:` replaces the node's parent and converts its position.
- SKSpriteNode: `isPointInside:` checks if a position point is inside of the sprite node's texture size.
- SKEmitterNode: `emitterLife` calculates an emitter's total life time.
- SKEmitterNode: `runActionToRemoveWhenFinished` adds an action which will remove the emitter if finished emitting.
- ... and some more additionals.


## Examples

There are two example projects one for each OS: iOS and OS X. They both use the same example scenes and tests and can be found inside of the Example directory.
To run an example project run `pod install` from the project directory first (cocoapods installed required).
Then open the workspace file INSpriteKitExample.xcworkspace with Xcode and run the example or the tests.
The example scenes are within the 'ExampleScenes' directory, just go through them to see how to use the library.

To see the difference between INSKView and SKView just rename the skView classes' name in the Storyboard (Xib-File for the OS X project).


## Requirements

iOS 7+ or OS X 10.9+, ARC enabled

Needs the following Frameworks:
- SpriteKit
- GLKit


## Installation

Add the following line to your Podfile:

	pod 'INSpriteKit', :git => 'https://github.com/indieSoftware/INSpriteKit.git'

or clone the repo manually, add the INSpriteKit directory to your project and add the necessary frameworks mentioned in the requirements section to your project.

Include the INSpriteKit.h header file to get access to all additions.

If using OS X and iOS code in the same project it may be handy to also include INSKOSBridge.h which adds some types and methods which are otherwise not available for the other OS.


**TODO** make available through CocoaPods so this will be true:

INSpriteKit is available through [CocoaPods](http://cocoapods.org), to install
it simply add the following line to your Podfile:

    pod "INSpriteKit"


## Version

Currently in work, no version released, yet!

[ChangeLog](./CHANGELOG.md)


## License

INSpriteKit is available under the MIT license. See the LICENSE file for more info.

