# bibtex-styles

These are the bibtex style files I (Yuji Tachikawa) regularly use. 
Both are based on Jacques Distler's U. Texas Austin style files, originally named `utphys.bst` and `utamsalpha.bst`.
Now you understood why these files are called `ytphys.bst` and `ytamsalpha.bst`.

- `ytphys.bst` follows the hep-th convention of numbering items as [1] [2] as they appear in the main text
- `ytamsalpha.bst` follows the math convention of labeling items as [Wit84] by combining the author name and the publication year

These style files accept bib entries produced by https://inspirehep.net/ and produce the bibliography with hyperlinks. 

Although I usually post to hep-th, I normally use ytamsalpha.bst as they provide more context for references when they appear each time in the main text.
And I habitually force my junior coauthors to agree to use it, as a dictatorial senior coauthor, which might be a workplace harrassment ...

# Two features of ytamsalpha.bst

## Font choice for arXiv:yymm.dddddd

The default is `\tt` but it can be overridden from the TeX file by including the line 
```
\arxivfont{\rm}
```
to make it roman, etc.

## Explicit ordering
ytamsalpha.bst tries to order the references according to their years of "publication",
which I define to be the earlier of the preprint year and the journal year. 
(Yes there are cases where people puts the preprint *after* it was published).
But there are edge cases where the automatically calculated order within the articles written by the same set of authors is not as it should be. 
In such cases you can insert the tag `sortOrder` by hand to force the ordering you like, such as:
```
@article{Article1,
sortOrder={1},
...
}
@article{Article2,
sortOrder={2},
...
}
```
This should force `Article2` to appear after `Article1`. The value of `sortOrder` is meaningful only within the same set of authors.
