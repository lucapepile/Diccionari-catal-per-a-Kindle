# Diccionari-catala-per-a-Kindle
Aquesta és una versió del DIEC2, utilitzable a Kindle. Està feta a partir de la versió .epub del diccionari, a partir de la qual s'ha construït la versió html (fitxer _content.html_) amb els criteris exigits per Amazon mitjançant reemplaçaments amb expressions regulars. A partir d'aquesta versió, s'hi ha afegit tota la morfologia nominal i verbal mitjançant el diccionari per al corrector Languagetool de Softcatala, gràcies al qual es pot distingir les paraules arrel del derivats; i totes les combinacions possibles amb apòstrofs, mitjançant també el corrector de Softcatala per al LanguageTool. Kindle, a diferència de com ho fa amb els guionets, no separa els apòstrofs de les paraules arrel a l'hora de fer les cerques al diccionari i per això ha sigut necessari fer aquest últim pas.
He creat tots els fitxers necessaris per poder exportar el diccionari a un format .mobi, mitjançant Kindle Previewer. El fitxer resultant s'ha de copiar mitjançant USB a la carpeta _documents > dictionaries_ del Kindle.

**Els passos a seguir són els següents:**  
1) Descarrega tots els documents en una carpeta, juntament amb el [diccionari.txt](https://github.com/Softcatala/catalan-dict-tools/blob/master/resultats/lt/diccionari.txt) de Softcatalà.  
2) Executa el codi _ordenar_diccionari.py_. Això crearà un fitxer morfologia.csv, amb tota la flexió nominal i verbal, amb la paraula arrel a la primera columna i totes les derivades a les columnes següents de la mateixa fila.
3) Executa el codi _afegir_apostrofs.py._ Aquest codi comprova les coincidències entre el fitxer _apostrofs.txt_ i _morfologia.csv_; en cas que hi hagi alguna paraula apostrofada del fitxer _apostrofs.txt_ que coincideixi amb alguna de les paraules del fitxer _morfologia.csv_, l'afegeix a continuació a la mateixa fila. Finalment, crea un fitxer nou anomenat _morfologia_i_apostrofs.csv_, amb tota la flexió verbal, nominal i totes les combinacions possibles amb apòstrofs.  El fitxer _apostrofs.txt_ és el resultat de generar una llista de totes les paraules possibles, incloent-hi apostrofació i pronoms febles per al corrector de LanguageTool, amb l'script [_build-wordlist-from-lt.sh_](https://github.com/Softcatala/catalan-dict-tools).
4) Executa el codi _partir_content.py_. Això crea una carpeta nova anomenada _parts_html_ i hi parteix el fitxer _content.html_ en 300 parts, ja que Kindle Previewer no pot processar correctament els fitxers grans.
5) Executa el codi _derivar_parts.py_. Això comprova si les entrades del diccionari dels fitxers partits coincideixen amb les paraules arrel del fitxer _morfologia_i_apostrofacio.csv_; en cas afirmatiu, afegeix tota la morfologia necessària a cada paraula que apareix al diccionari, perquè Kindle ho pugui reconèixer.
6) Finalment, obre el fitxer dicc.opf des de _Kindle Previewer 3_. Quan tingui tots els document html processats, exporta el contingut en un fitxer.mobi; aquest fitxer és el que s'ha de copiar a la carpeta _Diccionaris_ de Kindle.

Cal tindre el compte que els meus coneixements de programació són pràcticament nuls. Tot el codi ha estat escrit mitjançant IA. La meua feina, a base d'assaig error, ha consistit en ajustar-lo simplificant i ajustant al màxim les demandes al programador.    

**Pots descarregar el diccionari des [d'aquesta pàgina](https://diccionaricatalakindle.wordpress.com/).**
