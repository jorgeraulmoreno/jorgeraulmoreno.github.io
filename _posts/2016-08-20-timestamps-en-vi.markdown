---
published: true
title: timestamps en vi
layout: post
---
Para agregar timestamps a mis notas editadas con vi:

    :r !date
Para poner dos archivos side-by-side, en base a ...
    awk -F\| -v variable=$1 'BEGIN {ctr = 1} $1 == variable {if (antFN != FILENAME) {ctr = 1} print ctr,$1,$3,$4;ctr = ctr + 1;   antFN=FILENAME}' /path/to/filename1 > ~/one.txt;\
    awk -F\| -v variable=$1 'BEGIN {ctr = 1} $1 == variable {if (antFN != FILENAME) {ctr = 1} print ctr,$1,$3,$4;ctr = ctr + 1; antFN=FILENAME}' /path/to/filename2 > ~/two.txt;\
    pr -m -t ~/one.txt ~/two.txt | awk -v var2=$2 '$3 == var2 {print}'
