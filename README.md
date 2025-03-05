# Cub3D

Cub3D is a 3D game project inspired by the classic game Wolfenstein 3D. It is developed using the MinilibX, a graphic library to learn with.

## Setup

1. Download the project
    ```sh
    git clone https://github.com/dgaloiu/cub3d_.git cub3d
    ```
2. Download the MinilibX library from [mlx.fr](https://github.com/42Paris/minilibx-linux).
3. Copy the downloaded MinilibX to the `mlx_linux` directory inside the project folder:
    ```sh
    cp -r /path/to/minilibx-linux/* cub3d/mlx_linux
    ```
4. Run `make` to compile the project:
    ```sh
    cd cub3d
    make
    ```
5. Usage
    ```sh
    ./cub3d maps/the_map_you_want_to_try
    ```

## Changing Textures

To change the textures used in the game, modify the texture paths in the map file. For example, in the `map/map_4.cub` file:
```plaintext
// ...existing code...
NO texture/wall_1.xpm
WE texture/wall_2.xpm
EA texture/wall_3.xpm
SO texture/wall_4.xpm
// ...existing code...
```
Replace the paths with your desired texture files (xpm format only).

## Creating a Map

To create a new map, follow the structure of the existing map files. A map file consists of texture definitions and a grid representing the map layout. For example:
```plaintext
C 0,120,200
F 75,150,50
NO texture/wall_1.xpm
WE texture/wall_2.xpm
EA texture/wall_3.xpm
SO texture/wall_4.xpm

     11111111111111111111111       
    1000000000110000000000001
    1011000001110000000E000011
    100100000000000000000000111111111
    111111111011000001110000000000001
    100000000011000001110111111111101
11110111111111011100000000001     101
1110111111111011101000010001       1
11000000110101011100000010001
1110000000000000000000000001
11100000000000001101010010001
101000011101010111110111100111
11110111 1110101 10111101000001
11011111 1111111 1111111111111
101
11        1111
```
- `C` and `F` define the ceiling and floor colors respectively - in RGB format (from 0 to 255 for each color).
- `NO`, `WE`, `EA`, and `SO` define the textures for the north, west, east, and south walls.
- The grid uses `1` for walls, `0` for empty spaces, and `N` `S` `E` `W` for the player start position and orientation.
- The map must be `closed` or it won't work.

Save your map file in the `map` directory and update the game configuration to use your new map.
