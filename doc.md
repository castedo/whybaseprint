
# Diversity of Reading Venues

Multiple independent websites and applications can access a Baseprint document succession
to present the document in various ways.
Baseprint successions are not tied to a single website,
allowing readers the freedom to choose between alternative reading venues.

As of 2023, JATS XML [@enwiki:jats] is used to encode the contents of Baseprint
snapshots that make up a Baseprint succession.
A Baseprint snapshot gives readers the choice
between multiple web page formats,
similar to the choice between PubMed Central and journal websites.


# Document Succession Identifiers

A Document Succession Identifier (DSI) [@DSI_spec]
is an [intrinsic persistent identifier](
https://www.softwareheritage.org/2020/07/09/intrinsic-vs-extrinsic-identifiers/
) [@intrinsic_extrinsic_identifiers] of a Baseprint document succession.
It is a textual identifier similar to a
[DOI](https://en.wikipedia.org/w/index.php?title=Digital_object_identifier) [@enwiki:doi]
or a web address URL.
This document itself is archived as a Baseprint document succession with DSI:
```
dsi:wk1LzCaCSKkIvLAYObAvaoLNGPc
```

This is a *base DSI*, which identifies all snapshots within a Baseprint document succession,
both current and future.
Similar to textbooks and preprints,
Baseprint document successions contain multiple editions (or versions) of a Baseprint document,
each encoded as a
[Baseprint document snapshot](https://baseprints.singlesource.pub) [@what_is_baseprint].
A base DSI identifies all the editions of a document added to a Baseprint succession.
Usually, readers are interested in the latest edition in the Baseprint succession.

An edition number can follow a *base DSI* to identify a specific static edition.
For instance:
```
dsi:wk1LzCaCSKkIvLAYObAvaoLNGPc/1.1
```
identifies the earlier edition 1.1 of this document. Edition 1.1 will never change.


## Author-Owned Identifiers

A Baseprint succession is a work by an author, as declared by the author over time.
Unlike a traditional journal article, a Baseprint succession is not a single
final published result.
Unlike preprints on a preprint server,
a Baseprint succession is not a sequence of deposits at a specific preprint server.
A DSI identifies an author's work independently of where it is stored or viewed.

An author determines the editions in a Baseprint succession by digitally
signing the Baseprint succession with an SSH signing key.


<!-- copybreak on -->

## Multilevel Edition Numbering

Multilevel numbering is found in the numbering of
chapters, sections, and subsections (e.g., Chapter 2, Section 2.4, Subsection 2.4.3)
as well as software release versions (e.g., software release
2.19.2).
Authors of Baseprint successions can use multilevel numbering to identify editions
or stick to simple edition numbers of just positive integers,
like textbook editions and preprint version numbers.

Multilevel numbering is particularly useful when amending editions for a binary change
between Baseprint document snapshots but not in the intellectual content.
The DSI specification does not specify the meaning of different levels
in edition numbers, except that larger integers come after smaller integers, and
higher-level edition numbers identify subordinate sequences of lower-level edition numbers
(e.g., the entire sequence of edition numbers 2.1, 2.2, 2.3, ... can be identified by
edition number 2).

<!-- copybreak on -->

# Relationship to Git

While Git is normally used to store source code revisions,
it is not used for that exact purpose with Baseprint successions.
Git is used as a pragmatic implementation layer because it can handle distributed
data replication, digital signing, and cryptographic hashes.
The only history stored in a Baseprint succession is primarily the history of additions of
new editions to the succession.


# Conclusion

As of late 2023, Baseprint successions have been
implemented and used by the author for over a year.
Authors interested in publishing Baseprint successions can visit
[try.perm.pub](https://try.perm.pub/) to get started.

For technical details on how DSIs are implemented, see the [Document Succession
Identifier Specification](https://perm.pub/1wFGhvmv8XZfPx0O5Hya2e9AyXo) [@DSI_spec]
or the software library at
[gitlab.com/perm.pub/hidos](https://gitlab.com/perm.pub/hidos).


# Acknowledgments

This document was copyedited using
[CopyAid.it](https://copyaid.it), which uses OpenAI GPT-4.


# Changes

## From Edition 1.1 to 2.1

* The "digital succession" terminology has been update to "Baseprint document succession"
  terminology.
