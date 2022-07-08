# forge-viewer-svf2-loading-test-case

Test case of loading svf2 in various ways.

Just navigate to any of the html files in  the [public](./public) subfolder, for example:
- http://localhost:3000/AggregatedView.html?disableIndexedDb=true
- http://localhost:3000/MultipleModelUtil.html?disableIndexedDb=true

## Running locally

1. Get your Forge app client ID and client secret (see how to [create an app](https://forge.autodesk.com/en/docs/oauth/v2/tutorials/create-app))
2. Clone this repository, and navigate to the project's folder in your terminal
3. Install npm dependencies
    - `npm install`
4. Specify env. variables `FORGE_CLIENT_ID`, `FORGE_CLIENT_SECRET`, and `PORT`
    - `export FORGE_CLIENT_ID=<your client id>`
    - `export FORGE_CLIENT_SECRET=<your client secret>`
    - `export PORT=3000`
5. Run the app
    - `npm start`

If you're using [Visual Studio Code](https://code.visualstudio.com), skip the steps 4 and 5,
and instead create a _.vscode/launch.json_ in the project's folder with the following JSON:

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "skipFiles": [
                "<node_internals>/**"
            ],
            "program": "${workspaceFolder}/server.js",
            "env": {
                "FORGE_CLIENT_ID": "<your client id>",
                "FORGE_CLIENT_SECRET": "<your client secret>",
                "PORT": 3000
            }
        }
    ]
}
```

Then you can run _and debug_ the application with `F5`, or by going to `Run` > `Start Debugging`.

## Tips

- Always testing with Web Browser's [Incognito mode](https://support.google.com/chrome/answer/95464?hl=en&co=GENIE.Platform%3DAndroid) to avoid webpage cache issue.
- Add the extra query string `disableIndexedDb=true` to clear svf2 caches. e.g. http://localhost:3000?disableIndexedDb=true
- Add the extra query string `disableWebSocket=true` to load svf2 geometries without using WebSocket/under HTTP mode (**not recommended**, only for testing and debugging purpose). e.g. http://localhost:3000?disableWebSocket=true

# License

This sample is licensed under the terms of the [MIT License](http://opensource.org/licenses/MIT).
Please see the [LICENSE](LICENSE) file for full details.

## Written by

Eason Kang [@yiskang](https://twitter.com/yiskang), [Forge Partner Development](http://forge.autodesk.com)