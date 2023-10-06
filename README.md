# PitchSetClasses

A machine-readable version of Luis Nuño's List of Set Classes and Types

## Overview

This repository contains a single CSV file, containing the data in Appendix 2 of Luis Nuño's 2020 [paper](https://doi.org/10.1080/17459737.2020.1775902) "A Detailed List and a Periodic Table of [Set Classes](https://en.wikipedia.org/wiki/Set_(music))".  More specifically, the data available in the preprint [here](http://www.harmonicwheel.com/publicacion_4.pdf).

Like most [lists of set classes](https://en.wikipedia.org/wiki/List_of_set_classes), the table in the paper's appendix is arranged with complementary set classes across from each other on the same row. The file here, however, contains a single set class per line. The rows are sorted by Nuño's set class ordinal. This has the side-effect of sorting them in the order of increasing cardinality.

The various superscripts in the paper's table are given separate columns.

## Columns

### 0: cardinal

A number between 0 and 12, giving the number of [pitch classes](https://en.wikipedia.org/wiki/Pitch_class) in the set class.

### 1: ordinal

A number between 0 and 351, each occuring once.

### 2: complement

The ordinal of the set class that is the [complement](https://en.wikipedia.org/wiki/Complement_(music)#Aggregate_complementation) of the row's set class.

### 3: inversionallySymmetrical

Contains `true` if and only if the set class is inversionally symmetrical.

### 4: transpositionalSymmetry

The degree of transpositional symmetry for the set class. When this column is left blank, it means that the corresponding set class has transpositional symmetry of degree 1.

### 5: normalIF

The Intervallic Form is the intervals between every two adjascent pitch classes, including the interval between the last and the first ones. In the text of the paper these are notated with curly braces, like `{41421}`. This column contains the normal form of the set class's IF.

### 6: primeIFIsTypeB

Set classes that are chiral pairs (having `a` and `b` forms) usually have a prime IF that is type `a`. This column contains `true` if the prime form is type `b`. This column is left blank both in the case where the prime is type `a`, and also when the set class is inversionally symmetrical.

### 7: rahnNormalForm

The Rahn normal form of the set class. 

### 8: primeIsTypeB

Set classes that are chiral pairs have a prime Rahn normal form that is type `a`. This column contains `true` when the prime form is type `b`.

### 9: fortePrimeForm

The methods for calculating the prime forms given by Rahn and Forte differ for a few set classes. When they do, the prime form given by Forte appears in this column.

### 10: forteName

The extended Forte name of the set class.  In general, this is the cardinality of the set class, followed by the Forte ordinal separated by a hyphen. For set classes that are Z-related pairs, a `Z` appears before the ordinal. Finally, chiral pairs will have an `a` or a `b` at the end to indicate the set type.

### 11: zMateForteOrdinal

When a set class is part of a Z-related pair, the Forte ordinal of its mate appears in this column.

### 12: setTypeIsSelfComplementary

The complement of a set type `a` will be the `b`-type, and vice-versa, except for the two types of the set class with IF `{112143}`: `6-14a` and `6-14b`. These two are self-complementary, having the same TTV (Trichord Type Vector).  Type `a` corresponds to the prime IF.  These two rows have `true` in this column.

### 13: intervalVector

The ICV (Interval Class Vector) for this set class. This lists the number of times that each of the 6 dyads is contained in the set class.

### 14: trichordTypeVector

The TTV (Trichord Type Vector) is to trichords what the ICV is to dyads. It is a vector with 19 elements that lists the number of times that each of the possible 19 trichord types is contained within the given set type. For readability, these are divided into two groups separated by a hyphen. The first group includes the trichord types containing semitones, and the remaining trichords are in the second group. Refer to the paper for a detailed description.

Only two of the set types have the same TTV. The remainder have a unique TTV. Therefore, it fully characterizes their sonorities.
