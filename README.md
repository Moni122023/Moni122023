- 👋 Hi, I’m @Moni122023
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Moni122023/Moni122023 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
$source = 'D:\Folder1\'
 $destination = 'D:\Folder2\'
 $date = (Get-Date).AddDays(-10)
 Get-ChildItem -Path $source -Recurse -File |Where-Object {$_.LastWriteTime -ge $date} | ForEach-Object{
      $directory=$destination+($_.CreationTime).ToString('MM-dd-yyyy')
      if(-not (Test-Path -Path $directory)){
         New-Item -Path $directory -ItemType Directory
      } 
      Copy-Item -Path $_.FullName -Destination $directory
 }
