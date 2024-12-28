# Diccionari-catala-per-a-Kindle
Aquesta és una versió del DIEC2, utilitzable a Kindle. Està feta a partir de la versió .epub del diccionari, a partir de la qual s'ha construït la versió html (fitxer _content.html_) amb els criteris exigits per Amazon mitjançant reemplaçaments amb expressions regulars. A partir d'aquesta versió, s'hi ha afegit tota la morfologia nominal i verbal mitjançant el diccionari per a Hunspell de Sofcatalà. S'han creat tots els fitxers necessaris per poder exportar el diccionari a un format .mobi, mitjançant Kindle Previewer. El fitxer resultant és el que s'ha de copiar mitjançant USB a la carpeta _documents > dictionaries_ del Kindle.

**Els passos a seguir són els següents:**  
1) Descarrega tots els documents en una carpeta, juntament amb el [diccionari.txt](https://github.com/Softcatala/catalan-dict-tools/blob/master/resultats/lt/diccionari.txt) de Softcatalà.  
2) Executa el codi _ordenar_diccionari.py_. Això crearà un fitxer morfologia.csv, amb tota la flexió nominal i verbal, i apòstrofs perquè el diccionari ho pugui reconèixer.
3) Executa el codi _partir_content.py_. Això crearà una carpeta nova anomenada parts_html i hi partirà el fitxer content.html en 300 parts, ja que Kindle Previewer no pot processar els fitxers grans.
4) Executa el codi _derivar_parts.py_. Això comprovarà si les entrades del diccionari coincideixen amb les paraules arrel del fitxer morfologia.csv i en cas afirmatiu, afegirà tota la morfologia necessària a cada paraula que apareix al diccionari, perquè Kindle ho pugui reconèixer.
5) Obre el fitxer dicc.opf des del Kindle Previewer 3. Quan tingui tots els document html processats, exporta el contingut en un fitxer.mobi; aquest fitxer és el que s'ha de copiar a la carpeta _Diccionaris_ de Kindle.

Cal tindre el compte que els meus coneixements de programació són pràcticament nuls. Tot el codi ha estat escrit mitjançant IA. La meua feina, a base d'assaig error, ha consistit en ajustar-lo simplificant i ajustant al màxim les demandes al programador.  
Tanmateix, el diccionari presenta un hàndicap prou remarcable. La inclusió dels pronoms febles en forma elidida _m’, t’, s’_ i _n’_ als verbs que comencen per vocal incrementava d’una manera tan gran la quantitat de formes flexionades, que finalment Kindle només era capaç de reconèixer l’infinitiu d’aquests verbs. De manera que, sentint-ho molt, he hagut d’eliminar aquestes formes elidides del diccionari. O sigui que si per exemple busqueu la variant _«m’agraeix»_, el diccionari, que no és capaç de seleccionar només la paraula sense el pronom, no us tornarà cap resultat.
Pots descarregar el diccionari des [d'aquesta pàgina](https://diccionaricatalakindle.wordpress.com/).
