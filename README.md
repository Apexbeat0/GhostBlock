# Ghost Block

A client-side Fabric mod for Minecraft 26.2 that lets you locally hide blocks in your world using commands.

Ghost Block changes block states on your own client. The server's world state is not intentionally modified by the mod.

> **Warning:** This is an experimental project. Client-side block changes can cause client/server desynchronization and unexpected behavior. It has only been tested in a self-hosted multiplayer environment. Compatibility and behavior on other servers are not guaranteed. Use it responsibly and respect server rules.

## Features

- Hide the block you're currently looking at.
- Specify a custom raycast distance.
- Hide blocks inside a spherical radius.
- Filter radius-based hiding by block name.
- Undo the most recent hide operation.
- Restore all currently tracked hidden blocks.
- List hidden blocks and their coordinates.
- Automatically stop tracking blocks when the client receives the real block state again.

## Commands

| Command | Description |
|---|---|
| `/ghost` | Hide the block you're looking at. |
| `/ghost <range>` | Hide the targeted block using a custom reach distance (1–128). |
| `/ghost radius <n>` | Hide blocks within a spherical radius (1–16). |
| `/ghost radius <n> <blockname>` | Hide only the specified block type within the radius. |
| `/ghost undo` | Restore the most recent hide operation. |
| `/ghost clear` | Restore all currently tracked hidden blocks. |
| `/ghost list` | List hidden blocks and their coordinates. |
| `/ghost help` | Display the command list. |

Block names can be specified as `stone` or `minecraft:stone`.

## Requirements

- Minecraft **26.2**
- Java **25**
- Fabric Loader **0.19.3 or newer**
- Fabric API compatible with Minecraft 26.2

## Building from Source

Clone this repository:

```bash
git clone https://github.com/Apexbeat0/GhostBlock.git
cd GhostBlock
```

Build the mod:

**Linux / macOS**
```bash
chmod +x gradlew
./gradlew build
```

**Windows**
```bat
gradlew.bat build
```

The compiled JAR will be generated in:

```text
build/libs/
```

## Installation

1. Install Fabric Loader for Minecraft 26.2.
2. Install a compatible Fabric API version.
3. Build the project or obtain a compatible build.
4. Place the generated `ghostblock-1.0.5.jar` file in your Minecraft `mods` folder.
5. Launch Minecraft using the Fabric profile.

## How It Works

Ghost Block is a client-side-only mod. It stores the original block states locally and replaces selected positions with air on the client.

The mod keeps track of hidden positions and their original states. It also checks for server updates so that positions which have been restored by the server can be removed from its tracking data.

This means the visible world on the client can temporarily differ from the server's world state.

## Project Status

This is a small experimental project. It was created to explore client-side block manipulation and Minecraft client/server synchronization behavior.

It is provided as-is, without guarantees of compatibility with every server or future Minecraft version.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
