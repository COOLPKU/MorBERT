# MorBERT
Data for the paper "Disambiguate Words like Composing Them: A Morphology-Informed Approach to Enhance Chinese Word Sense Disambiguation" in ACL 2024

# General description
Our resources of Chinese WSD include two lexico-semantic inventories: morpheme inventory (**MorInv**) and word inventory (**WrdInv**), a Chinese WSD dataset (**M**orphology-**i**nformed **C**hinese **L**exical **S**ample dataset, **MiCLS**), and an out-of-vocabulary (**OOV**) test set. These constitute the largest and publicly available Chinese WSD resource so far as we know.

Note that we include monosemous words in MiCLS, which can largely benefit OOV sense representations and disambiguation. Some words unambiguous in dictionaries may have other OOV senses in real corpora, making them actually ambiguous. In Chinese, these issues are quite common.

Considering the demands of research, the data for our resources originates from the authoritative Chinese Contemporary Dictionary (CCD). To respect intellectual property rights and to better cater to computational applications, we have condensed the relevant semantic space to some extent, as well as largely revised and optimized the morpheme definitions and word definitions.

Here we have open-sourced a subset of this resource, encompassing 7,930 commonly used morphemes from the most frequently used 3,000 characters in Chinese. This includes:

- 7,930 entries from MorInv, covering 7,930 morphemes for 3,000 characters;
- 20,509 entries from WrdInv, covering 20,509 senses for 15,000 words;
- 80,078 entries from MiCLS, covering 18,844 senses for 15,000 words;
- Full dataset of the OOV test set, which contains 173 entries, covering 148 OOV senses for 147 words.

As a result, the experimental results in the paper may be slightly affected during replication.

These sampled resources are uploaded to `data/`. The file structure is as follows:

- `data/`: data files
  - `MorInv.txt`: Data for the morpheme inventory
  - `WrdInv.txt`: Data for the word inventory
  - `val.tsv`: the valid set of MiCLS
  - `test.tsv`: the test set of MiCLS
  - `OOV.tsv`: the OOV test set

Due to the restriction of file size, the training set of MiCLS is uploaded to [this link](https://pan.baidu.com/s/1oIcHmCYS87pac3F1ffWyqw?pwd=vyd4). (password: vyd4)

# Data format

**MorInv**
The file `MorInv.txt` contains entries in MorInv. The columns are separated by a space. The format and example of the data are shown in the table:
|Column|Description|Example|
|:----|:----|:----|
|**0**|Morpheme ID|月_1_07_03|
|**1**|Morpheme|月|
|**2**|PoS|名|
|**3**|Morpheme sense|月亮|

**WrdInv**
The file `WrdInv.txt` contains entries in WrdInv. The columns are separated by a space. The format and example of the data are shown in the table:
|Column|Description|Example|
|:----|:----|:----|
|**0**|Word ID|满月_0201|
|**1**|Word|满月|
|**2**|PoS|名|
|**3**|Word sense|圆月|

**MiCLS**
The files `train.tsv`, `val.tsv` and `test.tsv` contain the entries in MiCLS. The format and example of the data are shown in the table:
|Column|Description|Example|
|:----|:----|:----|
|**0**|Word|满月|
|**1**|Context|夜，静极了，玉盘似的#满月#在云中穿行，淡淡的月光洒向大地。|
|**2**|Definition|圆月|
|**3**|Formation|定中|
|**4**|Morpheme 1|整个|
|**5**|Morpheme 2|月亮|
|**6**|label|1|

**OOV test set**
The file `OOV.txt` contains entries in the OOV test set. The format and example of the data are shown in the table:
|Column|Description|Example|
|:----|:----|:----|
|**0**|Word|千万|
|**1**|Context|如今，顺德全区综合营收超～的设计企业达8家。|

## More Resources
For more work and resources related to the Chinese Object-Oriented Lexicon (COOL), Peking University, please refer to [this repository](https://github.com/COOLPKU) (to be released in the near future).


