gamepad.js for ImpactJS
======

This is a fork of gamepad.js (https://github.com/sgraham/gamepad.js) for use as a plugin with ImpactJS.

 * For more information about gamepad.js: http://www.gamepadjs.com/
 * For more information about ImpactJS: http://www.impactjs.com/

NOTES:

You will need a browser which supports the Gamepad API:

EXAMPLE:

Put the following in your main.js init:

        Gamepad.mappings.one = [
            [ 'dpadUp', 'up' ],
            [ 'dpadDown', 'down' ],
            [ 'dpadLeft', 'left' ],
            [ 'dpadRight', 'right' ],
            [ 'leftStickX', 'left', 'right' ],
            [ 'leftStickY', 'up', 'down' ],
            [ 'faceButton0, 'action1' ],
            [ 'faceButton1', 'action2' ],
            [ 'faceButton2, 'action3' ],
            [ 'faceButton3', 'action4' ]
        ];

And the following in your main.js update loop:

        Gamepad.handleInput();
        
If you're using Impact++, you have to override your handleInput instead:

        handleInput: function ()
        {
                this.parent();
                Gamepad.handleInput();
        }

AUTHORS:

 * Scott Graham (@h4kr, http://h4ck3r.net/)
 * ImpactJS and Linux modifications by Dan Wolfe (http://danwolfe.net)
 * Simpler usage modifications by Samuel Sarette
