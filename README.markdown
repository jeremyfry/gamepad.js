gamepad.js for ImpactJS
========================

This is a fork of gamepad.js (https://github.com/sgraham/gamepad.js) for use as a plugin with ImpactJS.

 * For more information about gamepad.js: http://www.gamepadjs.com/
 * For more information about ImpactJS: http://www.impactjs.com/

Note
------
You will need a browser which supports the Gamepad API:

How To Use
-----------

Put the following in your main.js init:

        Gamepad.mappings.one = [
            [ 'dpadUp', 'up' ],
            [ 'dpadDown', 'down' ],
            [ 'dpadLeft', 'left' ],
            [ 'dpadRight', 'right' ],
            [ 'leftStickX', 'left', 'right' ],
            [ 'leftStickY', 'up', 'down' ],
            [ 'faceButton0', 'action1' ],
            [ 'faceButton1', 'action2' ],
            [ 'faceButton2', 'action3' ],
            [ 'faceButton3', 'action4' ]
        ];

And the following in your main.js update loop:

        update: function()
        {
                Gamepad.handleInput();
                this.parent();
        }
        
###Impact++ Users

You have to include your mappings as above, however you should override your games handleInput instead of modifying the update loop:

        inputStart: function ()
        {
                this.parent();
                
                ig.input.bind(ig.KEY.X, 'jump');
                ig.input.bind(ig.KEY.C, 'tap');
                
                Gamepad.mappings.active = true;
        
        },
        
        inputEnd: function () 
        {
                this.parent();
                
                ig.input.unbind(ig.KEY.X, 'jump');
                ig.input.unbind(ig.KEY.C, 'tap');
                
                Gamepad.mappings.active = false;
        },
        
        handleInput: function () 
        {
                this.parent();
                Gamepad.handleInput();
        }

Authors
--------

 * Scott Graham (@h4kr, http://h4ck3r.net/)
 * ImpactJS and Linux modifications by Dan Wolfe (http://danwolfe.net)
 * Simpler usage and Impact++ compatibility modifications by Samuel Sarette
