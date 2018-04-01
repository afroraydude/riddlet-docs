# Configuration

Riddlet handles custom configurations through environment variables. 

## Configuration Parameters

`jwtcode`: The passcode used for signing JWT tokens. Set this if you don't want users to get new tokens on each server reboot (default: 15)

`riddlettitle`: The title of the server, used in the "Join Server" window of the client apps (default: Test Server)

`maxcharlen`: The maximum amount of characters allowed in a message (after decryption) (default: 500)

`logo`: The server's logo, used in the "Join Server" window of the client apps (default: https://d30y9cdsu7xlg0.cloudfront.net/png/29558-200.png)

`encrypt`: Set this to anything but "true" if you want to disable OTR-like message handling (default: true)
