gamepad.js for ImpactJS
======

This is a fork of gamepad.js (https://github.com/sgraham/gamepad.js) for use as a plugin with ImpactJS.

 * For more information about gamepad.js: http://www.gamepadjs.com/
 * For more information about ImpactJS: http://www.impactjs.com/

NOTES:

You will need a browser which supports the Gamepad API:

 * Google Chrome (Most Dev or Canary builds), Gamepad API can be activated on the chrome://flags page: http://dev.chromium.org/getting-involved/dev-channel

EXAMPLE:

Put the following in your main.js update loop:

        var gamepad = new Gamepad.getState(0);		
        var mappings = [[ gamepad.dpadUp, ig.KEY.UP_ARROW ],
                        [ gamepad.dpadDown, ig.KEY.DOWN_ARROW ],
                        [ gamepad.dpadLeft, ig.KEY.LEFT_ARROW ],
                        [ gamepad.dpadRight, ig.KEY.RIGHT_ARROW ],
                        [ gamepad.faceButton0, ig.KEY.X ],
                        [ gamepad.faceButton1, ig.KEY.C ],
                        [ gamepad.faceButton2, ig.KEY.Z ],
                        [ gamepad.faceButton3, ig.KEY.V ]];
        new Gamepad.magic(gamepad, mappings);
        
AUTHORS:

 * Scott Graham (@h4kr, http://h4ck3r.net/)
 * ImpactJS and Linux modifications by Dan Wolfe (http://danwolfe.net)

