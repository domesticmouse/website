{% assign os = include.os %}
{% assign target = include.target %}

To develop Flutter on {{os}}:

{% if os == "ChromeOS" %}

1. Enable [Linux][] on your Chromebook.

{% endif %}

1. Verify that you have the following tools installed:
   `bash`, `file`, `mkdir`, `rm`, `which`

   ```terminal
   $ which bash file mkdir rm which
   /bin/bash
   /usr/bin/file
   /bin/mkdir
   /bin/rm
   which: shell built-in command
   ```

1. Install the following packages:
   [`curl`][curl], [`git`][git], [`unzip`][unzip], [`xz-utils`][xz], [`zip`][zip], `libglu1-mesa`

   ```terminal
   $ sudo apt-get update -y && sudo apt-get upgrade -y;
   $ sudo apt-get install -y curl git unzip xz-utils zip libglu1-mesa
   ```

{% case target %}
{% when 'desktop' -%}

{% include docs/install/reqs/linux/install-desktop-tools.md devos=os %}

{% when 'Android' -%}

1. To develop {{target}} apps:

   {:type="a"}
   1. Install the following prequisite packages for Android Studio:
      `libc6:i386`, `libncurses5:i386`, `libstdc++6:i386`, `lib32z1`, `libbz2-1.0:i386`

      ```terminal
      $ sudo apt-get install \
          libc6:i386 libncurses5:i386 \
          libstdc++6:i386 lib32z1 \
          libbz2-1.0:i386
      ```

   1. Install [Android Studio][] {{site.appmin.android_studio}} to debug and compile
      Java or Kotlin code for Android.
      Flutter requires the full version of Android Studio.

{% when 'Web' -%}

1. Install [Google Chrome][] to debug JavaScript code for web apps.

{% include docs/install/accordions/install-chrome-from-cli.md %}

{% endcase -%}

[Linux]: https://support.google.com/chromebook/answer/9145439
[curl]: https://curl.se/
[git]: https://git-scm.com/
[unzip]: https://linux.die.net/man/1/unzip
[xz]: https://xz.tukaani.org/xz-utils/
[zip]: https://linux.die.net/man/1/zip
[Android Studio]: https://developer.android.com/studio/install#linux
[Google Chrome]: https://www.google.com/chrome/dr/download/
