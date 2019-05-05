## Minimalistic refind theme

[rEFInd](http://www.rodsbooks.com/refind/) is an easy to use boot manager for UEFI
based systems. This is a clean and minimal theme for it.

This theme is a combination of [rEFInd-minimal](https://github.com/EvanPurkhiser/rEFInd-minimal) and [refind-dreary](https://github.com/dheishman/refind-dreary)
![refind-theme](https://raw.githubusercontent.com/kvnbias/refind-theme/master/screenshot.jpg)

### Usage

 1. Locate your refind EFI directory. This is commonly `/boot/EFI/refind`
    though it will depend on where you mount your ESP and where rEFInd is
    installed. `fdisk -l` and `mount` may help.

 2. Create a folder called `themes` inside it, if it doesn't already exist

 3. Clone this repository into the `themes` directory.

 4. To enable the theme add `include themes/refind-theme/theme.conf` at the end of
    `refind.conf`.

Here's an example menuentry configuration (from the screenshot)

```
menuentry "Arch Linux" {
    icon /EFI/refind/themes/refind-theme/icons/os_arch.png
    loader vmlinuz-linux
    initrd initramfs-linux.img
    options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a"
}

menuentry "Windows" {
    icon /EFI/refind/themes/refind-theme/icons/os_win.png
    loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "macOS" {
    icon     /EFI/refind/themes/rEFInd-minimal/icons/os_mac.png
    volume   "Samsung SSD 850 EVO 500GB"
    loader   \System\Library\CoreServices\boot.efi
}
```

Entries that are autodetected should also show the proper icons.

### Background sizes

If you find the background looks blurry it may be due to the included wallpaper
being an incorrect resolution for your monitor. You can download the [original
high quality wallpaper][wallpaper], resize it as appropriate, and replace the
`background.png`.

You can of course also choose your own background!

### Attribution

The OS icons are from [Lightness for burg][icons] by [SWOriginal][icon-author].

The background is [Minimalist Wallpaper][wallpaper] by
[LeonardoAIanB][wallpaper-author]. Thank you to [Padster][padster] for locating
it!

[icons]: http://sworiginal.deviantart.com/art/Lightness-for-burg-181461810
[icon-author]: http://sworiginal.deviantart.com/

[padster]: https://github.com/theRealPadster
[wallpaper]: http://leonardoalanb.deviantart.com/art/Minimalist-wallpaper-295519786
[wallpaper-author]: http://leonardoalanb.deviantart.com/
