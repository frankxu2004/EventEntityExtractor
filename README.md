# Joint Event and Entity Extraction
Implementation of the joint event and entity model described in "Joint Extraction of Events and Entities within a Document Context" by Bishan Yang and Tom M. Mitchell.

If you are using this code in your work, please cite the following publication:

Bishan Yang and Tom Mitchell (2016). Joint Extraction of Events and Entities within a Document Context. Proceedings of the 2016 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (NAACL), pp. 289-299

For any questions/issues about the code, please feel free to email Bishan Yang (bishan.yang@gmail.com).

```latex
@InProceedings{yang2016joint,
  author    = {Yang, Bishan and Mitchell, Tom},
  title     = {Joint Extraction of Events and Entities within a Document Context},
  booktitle = {Proceedings of the 2016 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies},
  year      = {2016},
  pages     = {289--299}
}
```

## Compile the code
cmake

make

## Run the model
./JEE

## Example input
ace.test.conll: test documents in the CoNLL format

ace.test.dependencies.txt: the Stanford dependency parse outputs 

ace.test.stanford.ner.txt: the Stanford NER outputs

NER_Type  DocID  SentID  StartOffset,EndOffset

## Input

ace.test.conll stores the test documents in the CoNLL format:

DocID SentID TokenID Word POS Parse Lemma - - - - Tag

ace.test.dependencies.txt stores the Stanford dependency parse outputs for sentences in the test documents.

ace.test.stanford.ner.txt stores the named entity detected by Stanford NER using the following format:

NER_Type  DocID  SentID  StartOffset,EndOffset


## Output

joint.results.txt stores the extracted events, entities, and argument roles.

The outputs are organized according to the detected event triggers. For each trigger, we output its event type, and for each of its associated argument candidate, we output its entity type and role type: 

DocID#SentID#StartOffset#EndOffset  EventType

DocID#SentID#StartOffset#EndOffset#EntityType  RoleType

DocID#SentID#StartOffset#EndOffset#EntityType  RoleType

. . .


## References
CRF++: Yet Another CRF toolkit (https://taku910.github.io/crfpp/)

AD3 (approximate MAP decoder with Alternating Direction Dual Decomposition) (https://github.com/andre-martins/AD3)

Stanford CoreNLP version 3.6.0 (http://stanfordnlp.github.io/CoreNLP/)

## License
GNU Lesser General Public License v3.0
