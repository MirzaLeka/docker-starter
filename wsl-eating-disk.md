# Clean WSL space

Shut down WSL
```bash
> wsl -shutdown
```
Make sure the window is closed.

Run
```
Remove-Item "C:\Users\<user>\AppData\Local\Docker" -Recurse -Force
```
