# Try Out Development Containers: Python

This is a sample project that lets you try out the **[VS Code Remote - Containers](https://aka.ms/vscode-remote/containers)** extension in a few easy steps.

> **Note:** If you're following the quick start, you can jump to the [Things to try](#things-to-try) section. 

## Setting up the development container

Follow these steps to open this sample in a container:

1. If this is your first time using a development container, please follow the [getting started steps](https://aka.ms/vscode-remote/containers/getting-started).

2. To use this repository, you can either open the repository in an isolated Docker volume:

    - Press <kbd>F1</kbd> and select the **Remote-Containers: Try a Sample...** command.
    - Choose the "Python" sample, wait for the container to start and try things out!
        > **Note:** Under the hood, this will use **Remote-Containers: Open Repository in Container...** command to clone the source code in a Docker volume instead of the local filesystem.   

   Or open a locally cloned copy of the code:

   - Clone this repository to your local filesystem.
   - Press <kbd>F1</kbd> and select the **Remote-Containers: Open Folder in Container...** command.
   - Select the cloned copy of this folder, wait for the container to start, and try things out!

## Things to try

Once you have this sample opened in a container, you'll be able to work with it like you would locally. 

> **Note:** This container runs as a non-root user with sudo access by default. Comment out `"remoteUser": "vscode"` in `.devcontainer/devcontainer.json` if you'd prefer to run as root.

Some things to try:

1. **Edit:**
   - Open `app.py`
   - Try adding some code and check out the language features.

2. **Terminal:** 
    - Press <kbd>ctrl</kbd>+<kbd>shift</kbd>+<kbd>\`</kbd> to open a terminal window.
    - Type `python -m flask run --port 9000 --no-debugger --no-reload` to run the app.
    - Open a local browser and go to `http://localhost:9000` to see the running app.
    
      > **Tip:** If you use this container outside of VS Code via `docker run` with `-p 9000`, you may need to append `--host 0.0.0.0` to the command above. The `-p` option "publishes" the port rather than forwarding it. It therefore will not work if the application only listens to localhost. The `forwardPorts` property in `devcontainer.json` does not have this limitation, but you can use `appPort` property instead if you want to mirror the `docker run` behavior.

3. **Build, Run, and Debug:**
   - Open `app.py`
   - Add a breakpoint (e.g. on line 9).
   - Press <kbd>F5</kbd> to launch the app in the container.
   - Once the breakpoint is hit, try hovering over variables (e.g. the app variable on line 7), examining locals, and more.
   - Continue, then open a local browser and go to `http://localhost:9000` and note you can connect to the server in the container

4. **Forward another port:**
   - Stop debugging and remove the breakpoint.
   - Open `.vscode/launch.json`
   - Change the server port to 5000 on line 20. (`"--port","5000"`)
   - Press <kbd>F5</kbd> to launch the app in the container.
   - Press <kbd>F1</kbd> and run the **Forward a Port** command.
   - Select port 5000.
   - Click "Open Browser" in the notification that appears to access the web app on this new port.

5. **Run from the command line**
    - Press <kbd>ctrl</kbd>+<kbd>shift</kbd>+<kbd>\`</kbd> to open a terminal window   

### More samples

- [Tweeter App - Python and Django](https://github.com/Microsoft/python-sample-tweeterapp)

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## License

Copyright © Microsoft Corporation All rights reserved.<br />
Licensed under the MIT License. See LICENSE in the project root for license information.
