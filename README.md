# sawit-pro-ocr

This program is terminal based program that consist of 2 main command:
- `upload`, to upload image to Google Drive
- `extract`, to extract text from image to .docx files

## Technologies :
- Google Drive API
- Tesseract OCR
- Gradle (for package manager)

## How to Use :
- You need to setup Google Drive API permission. You can follow the instructions from its documentations This site was built using [here](https://developers.google.com/drive/api/quickstart/java)
- Save your `credentials.json` file to `src/main/resources` folder.
- Build the script using this command : `./gradlew clean build`
- To upload file to Google Drive, you must use this command :
```
java -jar <output_build>.jar upload <image_path>
```
the expected output will be like this, for example :
```
File ID: 1t46JXm2B2g4q43453tg34345g434g34
Web content link: https://drive.google.com/uc?id=1t46JXm2B2g4q43453tg34345g434g34&export=download
```
- To extract the text to .docx files, use this command :
```
java -jar <output_build>.jar extract <File ID>
```
- **NOTE**, if you have troubles running the program using those commands, it is recommended to run it with an IDE such as IntelliJ. But, don't forget to add the arguments when run it.

## Output Examples :
- Chinese text output (chinese_output.docx) :
<p align="center">
  <img src="./output/chinese-output.png">
</p>

- Alphabet text output (alphabet_output.docx) :
<p align="center">
  <img src="./output/alphabet-output.png">
</p>

<p align="center">
  <img src="./output/alphabet-output2.png">
</p>

- **NOTE**, Tesseract library has very limited capabilities. As I experimented, it will give unintended output for raw position texts. 

For example, if I use this image as input :
<p align="center">
  <img src="./input/ImageWithWords1.jpg">
</p>
I will get this output :
<p align="center">
  <img src="./output/alphabet-output3.png">
</p>