---
{"dg-publish":true,"permalink":"/02java//java-runtime-exe/","dgPassFrontmatter":true}
---

# java Runtime打开文本文件和图片,网址,音频,视频和exe文件等

## exe文件

今天听课的时候，老师提到了这个Runtime,但是老师举例子的时候用的是这个QQ.exe举例的

对于exe文件,我们只需要获得这个文本的绝对路径,然后用这个exec直接启动就行了

```java
import java.io.IOException;

public class OpenExeExample {
    public static void main(String[] args) {
        String exePath = "C:\\path\\to\\file.exe";
        openExe(exePath);
    }

    private static void openExe(String exePath) {
        try {
            Runtime.getRuntime().exec(exePath);
            System.out.println("应用程序已成功启动！");
        } catch (IOException e) {
            System.out.println("无法启动应用程序：" + e.getMessage());
        }
    }
}
```

## 图片和文本文件等

对于这个图片和文本文件我们不能直接通过这个Runtime,exec直接来打开,我们必须要在这个前面加上这个`"cmd /c start "`

这样才能打开这个文本文件和图片等

除此之外

通常情况下，`cmd /c start` 命令可以打开以下类型的文件：

- 文本文件（如 `.txt`、`.docx`、`.csv` 等）：可以使用默认文本编辑器打开。
- 图片文件（如 `.jpg`、`.png`、`.gif` 等）：可以使用默认图片查看器打开。
- 视频文件（如 `.mp4`、`.avi`、`.mov` 等）：可以使用默认视频播放器打开。
- 音频文件（如 `.mp3`、`.wav`、`.flac` 等）：可以使用默认音频播放器打开。
- PDF 文件（`.pdf`）：可以使用默认的 PDF 阅读器打开。
- 网址链接（如 `http://www.example.com`）：可以使用默认的浏览器打开网页。
- ...等等。