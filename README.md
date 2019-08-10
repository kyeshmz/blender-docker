
![Blender Logo](https://www.blender.org/wp-content/uploads/2015/03/blender_logo_socket.png)

# What is Blender?

[Blender](https://www.blender.org) is a free and open source 3D animation suite. It supports the entirety of the 3D pipeline—modeling, rigging, animation, simulation, rendering, compositing and motion tracking, even video editing and game creation. Advanced users employ Blender’s API for Python scripting to customize the application and write specialized tools; often these are included in Blender’s future releases. Blender is well suited to individuals and small studios who benefit from its unified pipeline and responsive development process.

# For GPU

# For CPU

# How to use this image

This image is intended to be used as a command line, render-only node for `.blend` files. You will need to create the 3D files beforehand using Blender's full GUI or download one from the many Blender file sharing sites like [Blend Swap](http://www.blendswap.com).

The entry point for this image is the blender non-gui command line `blender -b`. You can use the `/media/` directory to mount a volume with source files.

# Rendering a single frame

To render a single frame from a `blendfile.blend` file located in `/source/path` on the docker host and save the result in the same directory:

```console
$ docker run --rm -v /source/path/:/media/ ikester/blender /media/blendfile.blend -o /media/frame_### -f 1
```

This will create a file named `frame_001.png` in the same directory as the source file, assuming that PNG is the default output format for that file.

# Blender Command Line Reference

For additional information on Blender's command line parameters and options please visit the command line reference in the [Blender Reference Manual](https://www.blender.org/manual/render/workflows/command_line.html).

# License

This project is released under the MIT license. Please see the `LICENSE` file for details.
Forked originally from (ikester/blender-docker)[https://github.com/ikester/blender-docker/blob/master/README.md]

### Note: This is not an official Blender repository.
