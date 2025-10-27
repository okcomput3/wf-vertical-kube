# OLD VERSION WITHOUT CUBE CAPS, POPOUT WINDOWS AND BACKGROUND

# checkout https://github.com/okcomput3/wayfire-v-kube for new version


# Wayfire Vertical Kube Plugin

A Wayfire plugin that displays workspace rows as vertical cubes, allowing navigation between workspace rows in a 3D cube interface.

## Installation

Set `--prefix` to match your Wayfire installation path.
```bash
# For system-wide Wayfire installation
meson setup build --prefix=/usr

# Or for custom Wayfire installation
meson setup build --prefix=/opt/wayfire

# Build the plugin
meson compile -C build

# Install (requires sudo)
sudo meson install -C build
```

## Configuration

1. Edit your `~/.config/wayfire.ini`

2. Add `vertical_kube` to the plugins list in the `[core]` section:
```ini
   [core]
   plugins = ... vertical_kube
```
   **Important:** Remove the default `cube` plugin if present to avoid conflicts.

3. Configure bindings in the `[vertical_kube]` section:
```ini
   [vertical_kube]
   activate = <alt> <ctrl> BTN_LEFT
   rotate_left = <ctrl> <alt> KEY_LEFT
   rotate_right = <ctrl> <alt> KEY_RIGHT
   rotate_up = <ctrl> <alt> KEY_UP
   rotate_down = <ctrl> <alt> KEY_DOWN
   deform = 2
   light = true
```

4. Restart Wayfire

## Usage

- **Activate cube**: Hold `Alt+Ctrl` and click left mouse button, then drag to rotate
- **Rotate left/right**: `Ctrl+Alt+Left/Right` arrow keys
- **Move between workspace rows**: `Ctrl+Alt+Up/Down` arrow keys
- **Zoom**: Mouse wheel while cube is active

## Uninstallation
```bash
sudo ninja -C build uninstall
```

Or manually remove:
```bash
sudo rm /opt/wayfire/lib/x86_64-linux-gnu/wayfire/libvertical_kube.so
sudo rm /opt/wayfire/share/wayfire/metadata/vertical_kube.xml
```
