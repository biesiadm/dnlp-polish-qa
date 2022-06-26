1. Using https://github.com/attardi/wikiextractor parse wikipedia file from https://dumps.wikimedia.org/plwiki/latest/plwiki-latest-pages-articles.xml.bz2 to json command:
python3 -m wikiextractor.WikiExtractor plwiki-latest-pages-articles.xml.bz2 --json --templates 123.tmp
2. Using retriever from https://github.com/facebookresearch/DrQA retrieve tfidf from wikipedia files by commands:
python3 build_db.py /path/to/data /path/to/saved/db.db --preproces=./prep_wikipedia.py
python3 build_tfidf.py /path/to/doc/db /path/to/output/dir
3. Using distant from https://github.com/facebookresearch/DrQA prepare squad input:
Reformat questions to '{"question": "qN", "answer": []}'
python3 generate.py /path/to/dataset/dir dataset /path/to/output/dir --ranker=sqlite --db=db.db
4. Finally use reader 
