Small web image web downloader for acquiring image dataset.

First need to write some code in JS in order to get all the URLs we want to download the images.

You can start by going on google and make one image search.
Then follow these steps:
 - Open the JavaScript Console
 - on the images section scroll down until all the images you want appeared and the new ones appearing aren't that relevant.
 - On the JavaScript Console type:

var script = document.createElement('script');
script.src = "https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js";
document.getElementsByTagName('head')[0].appendChild(script);

 - Snippet above will pull down jQuery JavaScript library.
 - Below the above snippet type:

var urls = $('.rg_di .rg_meta').map(function() { return JSON.parse($(this).text()).ou; });

 - This snippet will grab all the URLs and save in one variable.
 - Below the snippet above type:

var textToSave = urls.toArray().join('\n');
var hiddenElement = document.createElement('a');
hiddenElement.href = 'data:attachment/text,' + encodeURI(textToSave);
hiddenElement.target = '_blank';
hiddenElement.download = 'urls.txt';
hiddenElement.click();

 - The snippet above will write all the URLs in one new file. Line per Line with all the URLs.
-----------------------------------------------------------------------

Now you should on the terminal you should go to the folder where you downloaded this code
type:
python3 web_downloader.py -u urls.txt -o images/santa



Tacio Degrazia.
03 Oct 2019