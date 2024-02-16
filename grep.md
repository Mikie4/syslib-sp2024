# Grep

## File upload

Since I am using docker desktop for the time being I thought I should include the upload and connection command.

![CMD](/img/image.png)

## Grep Tutorial

I initially followed the tutorial verbatim. I'm only including "interesting" screenshots.

![CMD](/img/image-1.png)

![CMD](/img/image-2.png)

Here is my command history

![CMD History](/imgimage-3.png)

# Grep

I used this command to see the different types of documents that were included in my search as well as show the count of each type.

```grep -i 'type =' scopus.bib | sort | uniq -c```

![Types](/img/image-4.png)

Next I decided I wanted to see how many documents exists that had more than 25 pages.

I started by using grep to find the lines with "pages ="

```grep "pages =" scopus.bib```

I then used AWK to filter out the range of page numbers the document was printed on, subtract to get the length of the document, increment a count whenever the calculated value was greater than 49, then print the count.

```
grep "pages =" scopus.bib | \
awk -F" |{|}" 'BEGIN { printf "Documents with more than 25 pages: "} \
{ if( $6 - $4 > 25 ) count++ } END { print count }
```

![CMD Pages](/img/image-5.png)