
# Output from gemini

You are absolutely right. Since you are using **Flatpak**, the issue is the same "sandbox" concept as Docker, but the fix is different.

By default, Flatpak apps are locked in a "security bubble" and **cannot** see your home folder (where your media is). You have to strictly give them permission.

Here is how to fix it.

### Step 1: Grant Permission (The Command)

Run this command in your terminal. It tells Flatpak to let Jellyfin see that specific folder:

```bash
sudo flatpak override org.jellyfin.JellyfinServer --filesystem=/home/handre/jellyfin-media
```

*Note: If you have other folders (like on your "My Passport" drive), you should run this command for those paths too, or just give it access to your whole media folder.*

### Step 2: Restart Jellyfin

The permission won't take effect until you restart the app.

1.  Close the Jellyfin tab in your browser.
2.  In the terminal, restart the app:
    ```bash
    flatpak kill org.jellyfin.JellyfinServer
    flatpak run org.jellyfin.JellyfinServer
    ```

### Step 3: Add the Library

Now go back to the Jellyfin dashboard (`http://localhost:8096`).

1.  Go to **Libraries** -\> **Add Media Library**.
2.  When you browse for the folder, you should now successfully be able to navigate to `/home/handre/jellyfin-media`.

**Pro Tip:** If you prefer clicking buttons instead of typing commands in the future, you can install an app called **Flatseal** from the Software Center. It lets you just toggle switches to give Flatpak apps access to folders.


# Notes
Remember to specify full path from root: 
```bash
/home/handre/jellyfin-media
```

