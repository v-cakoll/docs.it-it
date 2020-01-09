---
title: Implementazione di comportamenti discretionary nella classe XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d2758ea1-03f6-47bd-88d2-0fb7ccdb2fab
ms.openlocfilehash: b37cb0f4bf9a85053d70d549ae005c7d50a50bc0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710804"
---
# <a name="implementation-of-discretionary-behaviors-in-the-xsltransform-class"></a>Implementazione di comportamenti discretionary nella classe XslTransform

> [!NOTE]
> La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0. È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>. Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](migrating-from-the-xsltransform-class.md).

Sono definiti discretionary i comportamenti, elencati nella [versione 1.0 della raccomandazione W3C (World Wide Web Consortium) sulle trasformazioni XSL (XSLT)](https://www.w3.org/TR/1999/REC-xslt-19991116), nei quali il provider dell'implementazione sceglie una delle numerose opzioni disponibili per gestire una determinata situazione. Nella sezione 7.3 Creating Processing Instructions della raccomandazione W3C, ad esempio, viene specificato che la creazione di nodi diversi da nodi di tipo text durante la creazione di un'istanza del contenuto di `xsl:processing-instruction` costituisce un errore. Per alcuni problemi, il W3C fornisce una linea d'azione per il caso in cui il processore tenta di risolvere l'errore. Per l'errore illustrato nella sezione 7.3 viene spiegato che il problema può essere risolto ignorando i nodi e il relativo contenuto.

Pertanto, nella tabella seguente sono elencati, per ognuno dei comportamenti discrezionali consentiti da W3C, i comportamenti discrezionali implementati per l'implementazione .NET Framework della classe <xref:System.Xml.Xsl.XslTransform> e la sezione della raccomandazione W3C relativa a XSLT 1.0 in cui viene trattato questo problema.

|Problema|Comportamento di|Sezione|
|-------------|--------------|-------------|
|Nodo di tipo text corrispondente sia a `xsl:strip-space` sia a `xsl:preserve-space`.|Ripristina|3.4|
|Nodo di origine corrispondente a più di una regola dei modelli.|Ripristina|5.5|
|Un URI dello spazio dei nomi è dichiarato come alias per più URI dello spazio dei nomi, tutti con la stessa precedenza di importazione.|Ripristina|7.1.1|
|L'attributo del nome in `xsl:attribute` e `xsl:element` generato da un modello del valore dell'attributo non è un nome completo valido (QName).|Generazione di eccezione|7.1.12 e 7.1.3|
|Aggiunta di un attributo a un elemento dopo che al nodo dell'elemento sono già stati aggiunti nodi figlio.|Ripristina|7.1.3|
|Aggiunta di un attributo in una posizione diversa da un nodo Element.|Ripristina|7.1.3|
|L'istanza del contenuto dell'elemento `xsl:attribute` creata non è un nodo di tipo text.|Ripristina|7.1.3|
|Due set di attributi hanno la stessa precedenza di importazione e lo stesso nome espanso. Entrambi hanno lo stesso attributo e non sono presenti altri set di attributi contenenti l'attributo comune, con lo stesso nome e con un'importanza superiore.|Ripristina|7.1.4|
|`xsl:processing-instruction` non restituisce un nome senza due punti (NCName), né una destinazione dell'istruzione di elaborazione.|Ripristina|7.3|
|La creazione di un'istanza del contenuto `xsl:processing-instruction` crea nodi diversi da quelli di testo.|Ripristina|7.3|
|I risultati della creazione di un'istanza del contenuto di `xsl:processing-instruction` contengono la stringa "`?>`".|Ripristina|7.3|
|I risultati della creazione di un'istanza del contenuto di `xsl:comment` contengono la stringa "--" o terminano con "-".|Ripristina|7.4|
|I risultati della creazione di un'istanza del contenuto di `xsl:comment` creano nodi diversi da quelli di testo.|Ripristina|7.4|
|Il modello all'interno di un elemento di associazione della variabile restituisce un nodo Attribute o un nodo dello spazio dei nomi.|Ripristina|11.2|
|Si verifica un errore durante il recupero della risorsa dall'URI passato nella funzione del documento.|Generazione di eccezione|12.1|
|Il riferimento all'URI nella funzione del documento contiene un identificatore di frammento e si verifica un errore nell'elaborazione di tale identificatore.|Generazione di eccezione|12.1|
|Esistono più attributi con lo stesso nome che non sono denominati `cdata-section-elements` in `xls:output` e tali attributi hanno la stessa precedenza di importazione.|Ripristina|16|
|Il processore non supporta il valore di codifica dei caratteri fornito nell'attributo `encoding` dell'elemento `xsl:output`.|Ripristina|16.1|
|L'attributo `disable-output-escaping` viene usato per un nodo di tipo text che a sua volta viene usato per creare un elemento diverso da un nodo di tipo text nell'albero risultato.|L'attributo `disable-output-escaping` viene ignorato|16.4|
|Conversione di un frammento di albero risultato in un numero o stringa, se il frammento contiene un nodo di tipo text con l'escape dell'output abilitato.|Ignorato|16.4|
|L'escape dell'output è disabilitato per i caratteri che non possono essere rappresentati nella codifica usata dal processore XSLT per l'output.|Ignorato|16.4|
|Aggiunta di un nodo dello spazio dei nomi a un elemento dopo che a tale elemento sono stati aggiunti elementi figlio o attributi.|Ripristina|Errata e25|
|`xsl:number` è un valore NaN, infinito o minore di 0,5.|Ripristina|Errata e24|
|Il secondo set di nodi dell'argomento della funzione del documento è vuoto e il riferimento all'URI è relativo.|Ripristina|Errata e14|

Le sezioni Errata si trovano in [XSL Transformations (XSLT) Version 1.0 Specification Errata](https://www.w3.org/1999/11/REC-xslt-19991116-errata/) W3C.

## <a name="custom-defined-implementation-behaviors"></a>Comportamenti dell'implementazione definiti dall'utente

Alcuni comportamenti sono caratteristici solo dell'implementazione della classe <xref:System.Xml.Xsl.XslTransform>. Contenuto della sezione vengono descritte l'implementazione di `xsl:sort` specifica del provider e le funzionalità supportate dalla classe <xref:System.Xml.Xsl.XslTransform>.

## <a name="xslsort"></a>xsl:sort

Nella raccomandazione W3C XSLT 1.0 (informazioni in lingua inglese) sono contenute alcune osservazioni relative a come eseguire un ordinamento usando le trasformazioni. Ad esempio:

- Due processori XSLT possono essere conformi, ma potrebbero eseguire l'ordinamento ordinare in maniera differente.

- Non tutti i processori XSLT supportano le stesse lingue.

- In relazione alle lingue, è possibile che processori diversi eseguano l'ordinamento in modo diverso per una particolare lingua non specificata da `xsl:sort.`.

La tabella seguente mostra il comportamento di ordinamento implementato per ogni tipo di dati nell'implementazione .NET Framework di una trasformazione usando <xref:System.Xml.Xsl.XslTransform>:

|Tipo di dati|Modalità di ordinamento|
|---------------|----------------------|
|Testo|I dati vengono ordinati usando il metodo String.Compare di Common Language Runtime (CLR) e le impostazioni locali specifiche della lingua. Quando il tipo di dati risulta uguale a "text", l'ordinamento nella classe <xref:System.Xml.Xsl.XslTransform> si svolge in modo identico ai comportamenti nel confronto delle stringhe del CLR.|
|Number|I valori numerici vengono considerati come numeri XPath e vengono ordinati in base alle informazioni contenute nella [sezione 3.5 della raccomandazione W3C XML Path Language (XPath) versione 1.0](https://www.w3.org/TR/1999/REC-xpath-19991116/#numbers).|

## <a name="optional-features-supported"></a>Funzionalità opzionali supportate

Nella tabella seguente sono riportate le funzionalità la cui implementazione è facoltativa per un processore XSLT e che vengono implementate nella classe <xref:System.Xml.Xsl.XslTransform>.

|Caratteristica|Posizione del riferimento|Note|
|-------------|------------------------|-----------|
|Attributo `disable-output-escaping` sui tag `<xsl:text...>` e `<xsl:value-of...>`.|Raccomandazione W3C XSLT 1.0,<br /><br /> Sezione 16.4|L'attributo `disable-output-escaping` viene ignorato quando gli elementi `xsl:text` o `xsl:value-of` sono usati in un elemento `xsl:comment`, `xsl:processing-instruction`, o `xsl:attribute`.<br /><br /> I frammenti di albero risultato, che contengono testo e l'output di testo di cui è stato eseguito l'escape, non sono supportati.<br /><br /> L'attributo disable-output-escaping viene ignorato durante l'esecuzione di una trasformazione in un oggetto <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter>.|

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Xsl.XslTransform>
- [Implementazione del processore XSLT da parte della classe XslTransform](xsltransform-class-implements-the-xslt-processor.md)
- [Trasformazioni XSLT con la classe XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [XPathNavigator nelle trasformazioni](xpathnavigator-in-transformations.md)
- [XPathNodeIterator nelle trasformazioni](xpathnodeiterator-in-transformations.md)
- [Input di XPathDocument in XslTransform](xpathdocument-input-to-xsltransform.md)
- [Input di XmlDataDocument in XslTransform](xmldatadocument-input-to-xsltransform.md)
- [Input di XmlDocument in XslTransform](xmldocument-input-to-xsltransform.md)
