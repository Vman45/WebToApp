# Web To App

Examples of how to port a Web or HTML5 game to a native Android, iOS and Mac OS X App.

## How does it work

The App has a WebView that shows you the content of a embedded HTML file. Simple as that. So it doesn't require of an Internet connection to play your Web game.

## Porting details

| PORTING TO  | WORKS UNDER | READ FILES | WRITE FILES
| :------------ |:--------------- |:---------------: |:---------------:|
| iOS | iOS 13.0 or later | *In progress* | *In progress*
| OS X | OS X 10.12 or later | Yes | *In progress*
| Android | Android 5.0 or later | Yes | Yes

## Web example - How to read a file

```
<input type="file" onchange="readingAFile(event.target.files);"/>

<script>
   function readingAFile(files)
      {
      var filereader = new FileReader();
      filereader.file_name = files[0].name;
      filereader.onload = function()
         {
         var fileName = files[0].name;
         var fileContent = this.result;
         };
      filereader.readAsArrayBuffer(files[0]);
      }
</script>
```

## Web example - How to write a file

```
function download_Blob(data, fileName, mimeType)
   {
   var blob, url;
   blob = new Blob([data], {type: mimeType});
   url = window.URL.createObjectURL(blob);
   download_URL(url, fileName);
   }

function download_URL(data, fileName)
   {
   var a;
   a = document.createElement("a");
   a.href = data;
   a.download = fileName;
   document.body.appendChild(a);
   a.style = "display: none";
   a.click();
   a.remove();
   }

download_Blob("myData123", "MyFileName.txt", "application/octet-stream");
```

## How to get the .app file (for the OS X version only)

* Open the Mac project in Xcode.

* Click in **Product**.

* Click in **Archive**.

* Right click in the first item of the list and then click in **Show in Finder**.

* Right click in the **(ProductName).xcarchive** file.

* Click in **Show package contents**.

* Go to the **Products** folder.

* Go to the **Applications** folder.

* There is your .app file.

## Mac version

![alt screenshot](https://raw.githubusercontent.com/lrusso/WebToApp/master/Screenshot1.png)

## iOS version

![alt screenshot](https://raw.githubusercontent.com/lrusso/WebToApp/master/Screenshot2.png)

## Android version

![alt screenshot](https://raw.githubusercontent.com/lrusso/WebToApp/master/Screenshot3.png)

## Original Web version

https://lrusso.github.io/Spider/Spider.htm
