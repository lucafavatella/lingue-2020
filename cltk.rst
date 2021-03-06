Il Classical Language Toolkit (CLTK)
è una libreria Python
sotto licenza MIT
per l'elaborazione del linguaggio naturale.

>>> from cltk import NLP

Supporta le seguenti lingue.

>>> from cltk.nlp import iso_to_pipeline
>>> list(iso_to_pipeline.keys())
['akk', 'ang', 'arb', 'arc', 'chu', 'cop', 'enm', 'frm', 'fro', 'gmh', 'got', 'grc', 'hin', 'lat', 'lzh', 'non', 'pan', 'pli', 'san']

Fornisce un esempio di `avvio rapido <https://dev.cltk.org/en/latest/quickstart.html>`_,
previo scaricamento dei modelli.

>>> vitruvius = "Architecti est scientia pluribus disciplinis et variis eruditionibus ornata, quae ab ceteris artibus perficiuntur. Opera ea nascitur et fabrica et ratiocinatione."
>>> cltk_nlp = NLP(language="lat")
>>> cltk_doc = cltk_nlp.analyze(text=vitruvius)

>>> cltk_doc.tokens[:5]
['Architecti', 'est', 'scientia', 'pluribus', 'disciplinis']
>>> cltk_doc.words[1].string
'est'
>>> cltk_doc.words[1].stop
True
>>> cltk_doc.words[4].string
'disciplinis'
>>> cltk_doc.words[4].stop
False
>>> cltk_doc.words[4].lemma
'disciplina'
>>> cltk_doc.words[4].pos
noun
>>> cltk_doc.words[4].xpos
'C1|grn1|casO|gen3'
>>> cltk_doc.words[4].governor
8
>>> cltk_doc.words[8].string
'ornata'
>>> cltk_doc.words[4].dependency_relation
'obl'
>>> cltk_doc.words[4].embedding[:5]
array([-0.10924 , -0.048127,  0.15953 , -0.19465 ,  0.17935 ],
      dtype=float32)
>>> cltk_doc.words[5].index_sentence
0
>>> cltk_doc.words[20].index_sentence
1
