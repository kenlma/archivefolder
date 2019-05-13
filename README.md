# archivefolder
archive folders under current directory  and remove folders

for i in $(find . -maxdepth 1 -type d -mtime +30);
do
du -h --max-depth=0 $i
tar -zcf $i.tar.gz $i --remove-files
du -h $i.tar.gz;
done
