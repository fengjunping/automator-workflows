# Tunghsiao Liu’s Automator Workflows
A collection of Automator workflows that speed up your design and development process. Compatible with LaunchBar 6 and 7.

## Installation
Paste the following code at a Terminal prompt:

```shell
bash <(curl -fsSL https://raw.github.com/sparanoid/automator-workflows/go/install)
```

The script explains what it will do and then pauses before it does it. If you don’t trust it, [download zip package](https://github.com/sparanoid/automator-workflows/releases) and manually copy the workflows to `~/Library/Services/`.

## Available Workflows

### Create App Iconset
Create the following sizes of icon resources for your OS X app:

Filename | Size of canvas (in pixels)
--- | ---
icon_512x512@2x | 1024×1024
icon_512x512    | 512×512
icon_256x256@2x | 512×512
icon_256x256    | 256×256
icon_128x128@2x | 256×256
icon_128x128    | 128×128
icon_32x32@2x   | 64×64
icon_32x32      | 32×32
icon_16x16@2x   | 32×32
icon_16x16      | 16×16

The icon you created should be 1024×1024 with an sRGB color profile. You can read more about icon design guidelines [here](http://developer.apple.com/library/mac/documentation/userexperience/conceptual/applehiguidelines/IconsImages/IconsImages.html).

**Note**: You should always select the original file during the workflow, don’t press any key or click your mouse.

### Create .icns
Create .icns file using `iconutil`. Command Line Tools from Xcode must be installed before using this workflow.

### Unpack .icns
Unpack .icns into .iconset folder. Command Line Tools from Xcode must be installed before using this workflow.

### Create `favicon.ico`
Create 32x32 and 16x16 `favicon.ico` from selected PNG image with [ImageMagick](http://www.imagemagick.org/), `imagemagick` must be installed before using this workflow. Please note that since `imagemagick` is a third-party script, it’s [by design](http://developer.apple.com/library/mac/#technotes/tn2065/_index.html) that this script does NOT inherit the `$PATH` variable from your environment, you have to use full path for your `imagemagick` location, in this workflow, the path of `imagemagick` is `/usr/local/bin/imagemagick`. (Installed by [Homebrew](http://mxcl.github.io/homebrew/)).

### Add `@2x` Suffix
Add `@2x` suffix for retina image assets.

### Copy & Add `@2x` Suffix
Copy (duplicate) selected images and rename them with `@2x` suffix. Useful when you want to downscale with your own method.

### Create `@2x` Image
Auto downscale retina images generated by [PNG Express](http://www.pngexpress.com/), or any “@2x” images.

**Note**: Export your original images in retina size, WITHOUT `@2x` suffix.

### Remove `@2x` Suffix
Remove `@2x` suffix for retina image assets. Useful when you’re doing something wrong and need to recreate downscaled images one more time.

### Convert Image Format
Convert selected images to specific format.

### Resize Images
Resize your images to specific size or by percentage.

### Rename Selected Files

![Rename Finder Items](https://raw.github.com/sparanoid/rsrc/automator-workflows/01-rename-finder-items.png)

What? You just bought [A Better Finder Rename](http://www.publicspace.net/ABetterFinderRename/)?

### Create DMG Image
Create distributable, cross-platform hybrid DMG images using `hdiutil`, select a directory first to use this script. You’ll be prompted to enter a volume name for your image, then Voilà!

**Note**: This script doens’t create “fancy” DMG for your OS X app.

### Open with rmate
Open selected file with [rmate](https://github.com/textmate/rmate), `rmate` must be installed before using this workflow. Please note that since `rmate` is a third-party script, it’s [by design](http://developer.apple.com/library/mac/#technotes/tn2065/_index.html) that this script does NOT inherit the `$PATH` variable from your environment, you have to use full path for your `rmate` location, in this workflow, the path of `rmate` is `/usr/local/opt/ruby/bin/rmate` installed by [Homebrew](http://mxcl.github.io/homebrew/).

### Compress SVG
Compress selected SVG files with [svgo](https://github.com/svg/svgo), `svgo` must be installed before using this workflow. Please note that since `svgo` is a third-party script, it’s [by design](http://developer.apple.com/library/mac/#technotes/tn2065/_index.html) that this script does NOT inherit the `$PATH` variable from your environment, you have to use full path for your `svgo` location, in this workflow, the path of `svgo` is `/usr/local/bin/svgo`. (node and npm installed by [Homebrew](http://mxcl.github.io/homebrew/)).

### Compress PNG
Compress selected PNG files with [OptiPNG](http://optipng.sourceforge.net/), and [Pngcrush](http://pmt.sourceforge.net/pngcrush/), `optipng` and `pngcrush` must be installed before using this workflow. Please note that since `optipng` and `pngcrush` are third-party scripts, it’s [by design](http://developer.apple.com/library/mac/#technotes/tn2065/_index.html) that this script does NOT inherit the `$PATH` variable from your environment, you have to use full path for these binaries, in this workflow, `optipng` and `pngcrush` are located at `/usr/local/bin/`. (Installed by [Homebrew](http://mxcl.github.io/homebrew/)).

**Note #1**: The default `optipng` compress option is set to `-o7` (smallest file size and slowest), you may need change that.

**Note #2**: The default `pngcrush` compress option is set to `-brute -reduce -ow` (try 138 different methods and do lossless color-type or bit-depth reduction), you may need change that.

**Note #3**: `pngcrush` will take longer time for large images.

### Compress JPEG
Compress selected JPEG files with [jpegoptim](http://github.com/tjko/jpegoptim), `jpegoptim` must be installed before using this workflow. Please note that since `jpegoptim` is a third-party script, it’s [by design](http://developer.apple.com/library/mac/#technotes/tn2065/_index.html) that this script does NOT inherit the `$PATH` variable from your environment, you have to use full path for your `jpegoptim` location, in this workflow, the path of `jpegoptim` is `/usr/local/bin/jpegoptim`. (Installed by [Homebrew](http://mxcl.github.io/homebrew/)).

**Note**: The default compress option is set to `--strip-all --force --all-progressive` (lossless compression, remove comment, Exif and ICC profile, force all outputs to be progressive), You may need change that.

### Compress Images
This is a much simple workflow bundled with the three individual image compress workflows listed above. It auto detects the file type of selected images and compress them. `.png`, `.jpg` and `.svg` are supported. Of course `optipng`, `pngcrush`, `jpegoptim` and `svgo` must be installed before using this workflow.

**Note #1**: The default compress options for each type of images is the same as the individual compress workflow.

**Note #2**: It’s okay to run this workflow if you only install some of required dependencies, for example, you can just installed `optipng` and `jpegoptim`, but only `.png` and `.jpg` will be compressed when you run this workflow, all other SVG files you selected will be skipped.

### Encode Selected Files using Base64
Encode Selected Files using Base64 for [data URI scheme](http://en.wikipedia.org/wiki/Data_URI_scheme).

### Restart Finder
Restart your Finder without logging out or restarting your system.

:exclamation: **Note**: This workflow is a little bit different from others, in Mountain Lion or higher it can only be executed by Automator, that means you have to open this workflow in Automator and press Run button to execute it.

### Show Files
Toggle displaying hidden files, it’s also an workflow just like `Restart Finder.app`.

## Author
**Tunghsiao Liu**

- Twitter: @[tunghsiao](http://twitter.com/tunghsiao)
- GitHub: @[sparanoid](http://github.com/sparanoid)
