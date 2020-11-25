Start https://github.com/mau-jac/1T6-F20/raw/master/wk4/assets/file_compression.zip

cd ~

cd .\downloads\

Expand-Archive .\file_compression.zip

New-Item -Path .\assign_1 -ItemType Directory

mv .\file_compression\ .\assign_1\

New-Item -Path .\My_Documents\ -ItemType Directory

cd .\My_Documents\

New-Item -Path .\Other -ItemType Directory

New-Item -Path .\Texts -ItemType Directory

cd ..

New-Item -Path .\Shared\ -ItemType Directory

cd .\Shared\

New-Item -Path .\My_Images\ -ItemType Directory

cd ..

cd .\file_compression\file_compression\

mv .\Aristotle.docx ..\..\My_Documents\Texts

mv .\Brian_Kernighan.txt ..\..\My_Documents\Texts

mv .\Grace_Hopper.docx ..\..\My_Documents\Texts

mv .\Lindsay_Buckingham.docx ..\..\My_Documents\Texts

mv '.\Small Text.txt' ..\..\My_Documents\Texts

mv .\Unknown.txt ..\..\My_Documents\Texts

mv '.\Excel Worksheet.xlsx' ..\..\My_Documents\Other

mv .\question.png ..\..\Shared\My_Images\

mv .\Two_operators_ENIAC.gif ..\..\Shared\My_Images\

mv .\web.png ..\..\Shared\My_Images\

mv .\web.svg ..\..\Shared\My_Images\

cd ..

Remove-Item -Recurse .\file_compression

cd ..

Remove-Item -Recurse .\file_compression.zip

Compress-Archive ./assign_1 -DestinationPath assign_1.zip
