---
title: Documentazione XML (F#)
description: 'Informazioni sul supporto in F # per la generazione di documentazione da commenti.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: c9514532904f81030752bf7a4044f70a18222cab
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="xml-documentation"></a>Documentazione di XML

È possibile produrre la documentazione fornita dal triple-barra (/ / /) commenti in F # del codice. I commenti XML possono precedere le dichiarazioni nel file di codice (. FS) o file di firma (. fsi).


## <a name="generating-documentation-from-comments"></a>Generazione di documentazione da commenti
Il supporto in F # per la generazione di documentazione da commenti è uguale a quello in altri linguaggi .NET Framework. Come negli altri linguaggi .NET Framework, il [-opzione del compilatore /doc](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) consente di generare un file XML che contiene informazioni che è possibile convertire in documentazione utilizzando uno strumento come Sandcastle. La documentazione generata usando gli strumenti sono progettati per l'utilizzo con gli assembly che vengono in genere scritti in altri linguaggi .NET Framework per generare una vista delle API basata su form compilato dei costrutti di F #. A meno che non supporto degli strumenti in particolare F #, documentazione generata da questi strumenti non corrisponde alla visualizzazione di un'API F #.

Per ulteriori informazioni sulla generazione di documentazione da XML, vedere [commenti della documentazione XML &#40;C&#35; Guida per programmatori&#41;](https://msdn.microsoft.com/library/b2s063f7).


## <a name="recommended-tags"></a>Tag consigliati
Esistono due modi per scrivere commenti della documentazione XML. Uno consiste nello scrivere solo la documentazione direttamente in un commento barra tripla, senza l'utilizzo di tag XML. In questo caso, il testo del commento intero verrà considerato come la documentazione di riepilogo per il costrutto di codice che segue immediatamente. Utilizzare questo metodo quando si desidera scrivere solo un breve riepilogo per ogni costrutto. L'altro metodo consiste nell'utilizzare i tag XML per fornire una documentazione più strutturata. Il secondo metodo consente di specificare note separate per un breve riepilogo, osservazioni aggiuntive, documentazione per ogni parametro e un parametro di tipo e le eccezioni generate e una descrizione del valore restituito. La tabella seguente descrive i tag XML che sono riconosciuti nei commenti del codice XML di F #.



|Sintassi dei tag|Descrizione|
|----------|-----------|
|**&lt;c&gt;***testo***&lt;/c&gt;**|Specifica che *testo* è codice. Questo tag può essere utilizzato dai generatori di documentazione per visualizzare il testo in un tipo di carattere appropriato per il codice.|
|**&lt;riepilogo&gt;***testo*** &lt; /summary&gt;**|Specifica che *testo* viene fornita una breve descrizione dell'elemento del programma. La descrizione è in genere una o due frasi.|
|**&lt;la sezione Osservazioni&gt;***testo*** &lt; /remarks&gt;**|Specifica che *testo* contiene informazioni aggiuntive sull'elemento del programma.|
|**&lt;param name = "***nome***"&gt;***descrizione***&lt;/param&gt;**|Specifica il nome e descrizione per un parametro di funzione o metodo.|
|**&lt;typeparam name = "***nome***"&gt;***descrizione***&lt;/typeparam&gt;**|Specifica il nome e una descrizione per un parametro di tipo.|
|**&lt;Restituisce&gt;***testo*** &lt; /returns&gt;**|Specifica che *testo* descrive il valore restituito di una funzione o metodo.|
|**&lt;eccezione cref = "***tipo***"&gt;***descrizione***&lt;/exception&gt;**|Specifica il tipo di eccezione che può essere generati e le circostanze in cui viene generata.|
|**&lt;vedere cref = "***riferimento***"&gt;***text*** &lt; /vedere&gt;**|Specifica un collegamento inline a un altro elemento del programma. Il *riferimento* è il nome visualizzato nel file di documentazione XML. Il *testo* è il testo visualizzato nel collegamento.|
|**&lt;seealso cref = "***riferimento***" /&gt;**|Specifica un collegamento Vedere anche la documentazione per un altro tipo. Il *riferimento* è il nome visualizzato nel file di documentazione XML. Vedere anche in genere visualizzati nella parte inferiore della pagina di documentazione di collegamenti.|
|**&lt;para&gt;***testo***&lt;/para&gt;**|Specifica un paragrafo di testo. Viene utilizzato per separare il testo all'interno di **osservazioni** tag.|

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione
Di seguito è un commento di documentazione XML tipico in un file della firma.


### <a name="code"></a>Codice
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]
    
## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione
Nell'esempio seguente viene illustrato il metodo alternativo, senza tag XML. In questo esempio, tutto il testo nel commento è considerato un riepilogo. Si noti che se non si specifica un tag di riepilogo in modo esplicito, è necessario non specificare altri tag, ad esempio **param** o **restituisce** tag.


### <a name="code"></a>Codice
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]
    
## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Opzioni del compilatore](compiler-options.md)
