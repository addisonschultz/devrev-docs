# Install DevRev CLI

The DevRev CLI is a command-line interface tool that simplifies working with the DevRev REST APIs.

<Tabs>
  <Tab title="Debian">
    ## Supported architectures:

    * Linux amd64
    * Linux arm64

    ## Installation

    [Download the Debian package](https://github.com/devrev/cli/releases/latest) and install it using the following command:

    ```bash
    sudo dpkg -i devrev_0.4.0-linux_amd64.deb
    ```

    or

    ```bash
    sudo dpkg -i devrev_0.4.0-linux_arm64.deb
    ```

    Run the following command to install the completions:

    ```bash
    wget https://raw.githubusercontent.com/devrev/cli/main/install_completions.sh && sh install_completions.sh /usr/local/bin/devrev
    ```

    <Callout intent="note">
      The Debian path `/usr/local/bin/devrev` may vary based on your Debian installation.
    </Callout>

    ## Uninstallation

    ```bash
    sudo dpkg -r devrev
    ```
  </Tab>

  <Tab title="MacOS">
    ## Supported architectures:

    * Darwin amd64
    * Darwin arm64
    * Linux arm64
    * Linux amd64

    ## Installation

    Download the Homebrew formula [devrev.rb](https://github.com/devrev/cli/releases/latest/download/devrev.rb) or run the following command:

    ```bash
    wget https://github.com/devrev/cli/releases/latest/download/devrev.rb
    ```

    Install the downloaded Homebrew formula file devrev.rb using the following command:

    ```bash
    brew install ./devrev.rb
    ```

    Run the following command to install the completions:

    ```bash
    wget https://raw.githubusercontent.com/devrev/cli/main/install_completions.sh && sh install_completions.sh /opt/homebrew/bin/devrev
    ```

    <Callout intent="note">
      The Homebrew path `/opt/homebrew/bin/devrev` may vary based on your Homebrew installation
    </Callout>

    ## Uninstallation

    ```bash
    brew uninstall devrev
    ```
  </Tab>

  <Tab title="Windows">
    ## Supported architectures:

    * Windows amd64

    ## Installation

    Download the [Windows executable](https://github.com/devrev/cli/releases/latest).

    Unzip the downloaded file and add the path to the environment variable.

    Add the directory to the system PATH variable under **System Properties** > **This PC** > **Properties**.

    In the System window, click **Advanced system settings** > **Environment Variables** > **Path** > **Edit**.
    In the **Edit environment variable** window, click **New**. Enter the path to the directory you want to add. For example: `C:\Program Files\devrev\`
    Click **OK** to save the changes. Close all remaining windows by clicking **OK**.

    <Callout intent="note">
      You may need to restart your computer for the changes to take effect.
    </Callout>

    ## Uninstallation

    1. Remove the path from the environment variable.
    2. Delete the downloaded executable file and its folder.
  </Tab>
</Tabs>