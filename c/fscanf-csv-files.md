# fscanf with CSV Files

One can use `fscanf` to read formatted input files, such as space/comma/pipe/tab delimited files, into C. Most of the formats used in specifying the file format are straight forward with things like ints, float, and bools for fields in the input file. But something interesting happens when your file contains string fields and is not separated by whitespace. In this case, your delimiter can actually be assumed into the string field and give an error at runtime. So say, you have a file like the following:

```csv
dog,3
cat,10
mouse,4
leopard,25
```

If you were to use the following call to `fscanf` (Hint: The format parameter is the important part!), then you would get an error at runtime.

```c
char *animal[25];
int label;

FILE *fp;
fp = fopen("my-file.csv","r");

if (fp) {
    while(fscanf(fp,"%s,%d",animal,&label) != EOF) {
        printf("Animal:\t%s, Label:\t%d", animal, label);
    }
}


fclose(fp);
```

Instead, you should use the following notation in the format to tell C that you want to look for a string up to 25 characters or until you reach a comma: `%25[^,]`. Thus, the above call to `fscanf` would actually change to

```c
fscanf(fp,"%25[^,],%d",animal,&label)
```

This will read in a string of upto 25 characters or stop reading in a string once it hits a comma in the file and move on to the next field.