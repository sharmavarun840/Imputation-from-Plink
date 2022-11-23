# Imputation-from-Plink
input : data.ped and dat.map

>plink --file data --make-bed

gives data.bim, data.bed, data.fam


download [from hapmap/1000gen] refdata
http://grch37.ensembl.org/Homo_sapiens/Tools/VcftoPed

ped and map files, here named GIH.ped and GIH.map

>plink --file GIH --make-bed

gives GIH.bim, GIH.bed, GIH.fam

now, merge files

>plink --bfile GIH --bmerge data.bed data.bim data.fam --make-bed --out
merged

gives merged.bim, merged.bed, merged.fam

run imputing
>plink --bfile merged --proxy-impute rs17846866
or
>plink --bfile merged-1 --proxy-assoc all
or
>plink --bfile merged --proxy-impute rs17846866  --proxy-verbose
