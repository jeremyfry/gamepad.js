gamepad.js for ImpactJS
======

This is a fork of gamepad.js (https://github.com/sgraham/gamepad.js) for use as a plugin with ImpactJS.

 * For more information about gamepad.js: http://www.gamepadjs.com/
 * For more information about ImpactJS: http://www.impactjs.com/

NOTES:

You will need a browser which supports the Gamepad API:

EXAMPLE:

Put the following in your main.js update loop:

        var gamepads = new Gamepad.getStates();
        if (gamepads.length > 0 && typeof(gamepads[0]) != "undefined" )
        {
            ig.gamepad = gamepads[0];
            var mappings = [
            [ ig.gamepad.dpadUp, 'up' ],
            [ ig.gamepad.dpadDown, 'down' ],
            [ ig.gamepad.dpadLeft, 'left' ],
            [ ig.gamepad.dpadRight, 'right' ],
            [ ig.gamepad.leftStickX, 'left', 'right' ],
            [ ig.gamepad.leftStickY, 'up', 'down' ],
            [ ig.gamepad.faceButton0, 'action1' ],
            [ ig.gamepad.faceButton1, 'action2' ],
            [ ig.gamepad.faceButton2, 'action3' ],
            [ ig.gamepad.faceButton3, 'action4' ]
            ];
            new Gamepad.magic(ig.gamepad, mappings);
        }
        
AUTHORS:

 * Scott Graham (@h4kr, http://h4ck3r.net/)
 * ImpactJS and Linux modifications by Dan Wolfe (http://danwolfe.net)
 * "Map to Action not Keys" fork by Samuel Sarette
