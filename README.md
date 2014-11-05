# Node.js Tool Bundle

Symfony 2 bundle which integrates npm and bower with composer.

Mainly used for personal projects, but might be useful to others.
Probably only works on \*nix and Mac OS X, since it uses `which` to find __bower__ and __npm__


### Instructions

To use, put this in composer.json somewhere at the buttom.

```json
{
    ...
    "scripts": {
        "post-install-cmd": [
            ...
            "Dsbaars\\Bundle\\NodejsToolBundle\\Composer\\ScriptHandler::checkToolAvailability",
            "Dsbaars\\Bundle\\NodejsToolBundle\\Composer\\ScriptHandler::installNpmAssets",
            "Dsbaars\\Bundle\\NodejsToolBundle\\Composer\\ScriptHandler::installBowerAssets"
        ],
        "post-update-cmd": [
            ...
            "Dsbaars\\Bundle\\NodejsToolBundle\\Composer\\ScriptHandler::checkToolAvailability",
            "Dsbaars\\Bundle\\NodejsToolBundle\\Composer\\ScriptHandler::installNpmAssets",
            "Dsbaars\\Bundle\\NodejsToolBundle\\Composer\\ScriptHandler::installBowerAssets"
        ]
    }
}
```
