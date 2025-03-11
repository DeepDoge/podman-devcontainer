# podman-devcontainer  

A simple `podman` wrapper to make it work with DevContainers. Just a quick way to get Podman playing nice with your dev setup.  

## Usage  

1. Create a script file at `~/.local/bin/podman-devcontainer` (or anywhere in your `PATH`).  
2. Copy-paste the script in.  
3. In VS Code, add this to your settings (or do something similar in your editor):  
   ```json
   {
     "dev.containers.dockerPath": "podman-devcontainer"
   }
   ```  
4. Done! 🎉  

### Using with Distrobox  

If you're running `distrobox`, you'll want to create another wrapper to make sure it runs outside the container:  

```bash
#!/bin/bash
distrobox-host-exec podman-devcontainer "$@"
```  

This ensures `podman-devcontainer` runs on the host instead of inside `distrobox`.  

Personally, I use a separate home directory for `distrobox`, which makes keeping things organized even easier.

### Alternative Setup  

If you’re not using Docker (like me), you can just name it `docker` instead. That way, you don’t have to tweak DevContainer settings for every editor or IDE.  

---

Been using this setup for over a year—zero issues. Works like a charm! 🚀  
