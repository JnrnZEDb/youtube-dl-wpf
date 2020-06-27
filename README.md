# 🎞⬇ Cube YouTube Downloader - `youtube-dl-wpf`

A simple GUI wrapper for [`youtube-dl`](https://github.com/ytdl-org/youtube-dl). _A ported cross-platform version is available as [`youtube-dl-avalonia`](https://github.com/database64128/youtube-dl-avalonia)._

![Light Mode](LightMode.png "Light Mode")
![Dark Mode](DarkMode.png "Dark Mode")

## Features

- Toggle 🌃 Dark Mode and 🔆 Light Mode.
- Update `youtube-dl` on startup.
- List available formats.
- Override video and audio formats.
- Toggle metadata embedding.
- Toggle thumbnail and subtitles embedding.
- Toggle downloading a single video or the whole playlist.
- Custom download path.
- Custom `ffmpeg` and `youtube-dl` path.
- Custom proxy support.

## Usage

1. Download the pre-built binary or build it from source.
2. Download [`youtube-dl`](https://github.com/ytdl-org/youtube-dl) from the upstream. _Optionally but recommended_, get `ffmpeg` either by [building from source](https://www.ffmpeg.org/) or downloading [pre-built binaries](https://ffmpeg.zeranoe.com/builds/) for Windows.
3. Make sure you have [.NET Core 3.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/current/runtime) installed to run our app. The upstream `youtube-dl` binary requires [MSVC++ 2010 runtime](https://www.microsoft.com/en-us/download/details.aspx?id=13523).
4. Run `youtube-dl-wpf.exe`. Open the left drawer and go to __Settings__. Set the path to `youtube-dl` and `ffmpeg`.
5. Go back to the home tab. Paste a URL and start downloading! 🚀

## F.A.Q.

- _Q:_ The __Download__ button is grayed out and I can't click it!
- _A:_ `youtube-dl-wpf` is a simple GUI wrapper. It doesn't embed any downloader in it. You have to download `youtube-dl` from the upstream. The `ffmpeg` binary is required by `youtube-dl` when downloading and merging separate video and audio tracks, which is the case for any video resolution higher than 360p.

- _Q:_ How can I specify video and audio tracks to download?
- _A:_ First use the "List Formats" button to ask youtube-dl to list all available formats. To specify the video and audio format, toggle "Override Formats" and fill in the format numbers, as shown in the screenshots above.

- _Q:_ How can I use a proxy to download?
- _A:_ Leave the proxy field empty to use system proxy settings. Otherwise the format is similar to how `curl` accepts proxy strings. Examples are, `socks5://localhost:1080/`, `http://localhost:8080/`. Currently the upstream doesn't accept `socks5h` protocol and treat `socks5` as `socks5h` by always resolving the hostname using the proxy. This is tracked in [this issue](https://github.com/ytdl-org/youtube-dl/issues/22618).

- _Q:_ Downloading the whole playlist doesn't work!
- _A:_ It's an upstream bug, just like many other issues you might discover. There's nothing I can do. Just report the bug to the [upstream](https://github.com/ytdl-org/youtube-dl).

## Known Issues

- Setting `youtube-dl` path won't update button status.
- Changing window size when texts are wrapped in the `resultTextBox` results in an enlarged TextBox that won't scale down.

## Build

- IDE: Visual Studio 2019
- Language: C# 8.0
- Framework: .NET Core 3.1

### Steps

1. Clone the repository recursively.
```bash
$ git clone --recursive https://github.com/database64128/youtube-dl-wpf.git
```
2. Open the repository in VS2019, switch to the _Release_ configuration, and build the solution.

## To-Do

- Re-implement `AppSettings`.

## License

`youtube-dl-wpf` is licensed under [GPLv3](LICENSE).

[`youtube-dl`](https://github.com/ytdl-org/youtube-dl) is licensed under [The Unlicense](https://github.com/ytdl-org/youtube-dl/blob/master/LICENSE).

[Material Design Themes](https://github.com/MaterialDesignInXAML/MaterialDesignInXamlToolkit) is licensed under [MIT](https://github.com/MaterialDesignInXAML/MaterialDesignInXamlToolkit/blob/master/LICENSE).
