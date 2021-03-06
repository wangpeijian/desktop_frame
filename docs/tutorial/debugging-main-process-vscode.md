# 使用 VSCode 进行主进程调试

### 1.在 VSCode 中打开一个 Electron 项目。

```sh
$ git clone git@github.com:electron/electron-quick-start.git
$ code electron-quick-start
```

### 2.添加一个 `.vscode/launch.json` 文件并使用以下配置：

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Main Process",
      "type": "node",
      "request": "launch",
      "cwd": "${workspaceRoot}",
      "runtimeExecutable": "${workspaceRoot}/node_modules/.bin/electron",
      "windows": {
        "runtimeExecutable": "${workspaceRoot}/node_modules/.bin/electron.cmd"
      },
      "args" : ["."]
    }
  ]
}
```

**注意：** 在 Windows 中，`runtimeExecutable` 的参数是 `"${workspaceRoot}/node_modules/.bin/electron.cmd"`。

### 3. 调试

在 `index.js`中设置一些断点，并在 [Debug 视图](https://code.visualstudio.com/docs/editor/debugging) 中开始调试。你应该能够捕获断点信息。

这是一个预先配置的项目，你可以下载并直接在 VSCode中调试: https://github.com/octref/vscode-electron-debug/tree/master/electron-quick-start