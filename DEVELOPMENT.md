# How to Develop Netron

Netron can run as both an [Electron](https://electronjs.org) app or a Python web server.

## Develop the Electron app

The start the Electron app, install [Node.js](https://nodejs.org) and run: 

```bash
npm install
npx electron .
```

To debug the Electron app use [Visual Studio Code](https://code.visualstudio.com) and install the [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) extension. Open the `./Netron` root folder in Visual Studio Code and press `F5`. To attach the debugger to the actual rendering window select the `Debug` tab and `Debug Renderer Process` before launching.

To build full Electron app binaries to the `./build/electron` folder run `electron-builder`:

```bash
npx electron-builder --mac --linux --win
```

## Develop the Python server

To build and launch the python server run:

```bash
npm install
python ./setup.py --quiet build
PYTHONPATH=./build/python/lib python ./build/python/scripts-2.7/netron [...]
```

The same can be accomplished by running the `./netron` script in the enlistment root folder.
