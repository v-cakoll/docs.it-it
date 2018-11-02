---
title: Documentazione XML (F#)
description: 'Informazioni sul supporto in F # per la generazione di documentazione da commenti.'
ms.date: 05/16/2016
ms.openlocfilehash: 1a4cb132e65b630821e5eb2b39276c1de99aff80
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45641625"
---
# <a name="xml-documentation"></a>Documentazione di XML

È possibile produrre documentazione dai tripla barra (/ / /) nei commenti in F # del codice. Commenti in formato XML può precedere le dichiarazioni nel file di codice (. FS) o file di firma (. fsi).

## <a name="generating-documentation-from-comments"></a>Generazione di documentazione dai commenti

Il supporto in F # per la generazione di documentazione dai commenti è uguale a quello in altri linguaggi .NET Framework. Come negli altri linguaggi .NET Framework, il [-l'opzione del compilatore doc](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) consente di produrre un file XML che contiene informazioni che è possibile convertire in documentazione usando uno strumento come Sandcastle. La documentazione generata usando gli strumenti progettati per l'uso con gli assembly che vengono scritti in altri linguaggi .NET Framework in genere produce una visualizzazione delle API basata su form compilato dei costrutti di F #. A meno che gli strumenti in modo specifico supportano F #, documentazione generata da questi strumenti non corrisponde alla visualizzazione F # di un'API.

Per altre informazioni su come generare documentazione da XML, vedere [commenti in formato documentazione XML &#40;C&#35; Guida alla programmazione di&#41;](https://msdn.microsoft.com/library/b2s063f7).

## <a name="recommended-tags"></a>Tag consigliati

Esistono due modi per scrivere commenti in formato documentazione XML. Uno consiste nello scrivere semplicemente la documentazione direttamente in un commento con barra tripla, senza usare i tag XML. Se in questo caso, il testo del commento intero viene eseguito come documentazione di riepilogo per il costrutto di codice che segue immediatamente. Utilizzare questo metodo quando si desidera scrivere solo un breve riepilogo per ciascun costrutto. L'altro metodo consiste nell'utilizzare i tag XML per fornire più strutturata documentazione. Il secondo metodo consente di specificare note separate per un breve riepilogo, osservazioni aggiuntive, documentazione per ogni parametro e il parametro di tipo e le eccezioni generate e una descrizione del valore restituito. La tabella seguente descrive i tag XML che sono riconosciuti nella commenti al codice F #. XML.

|Sintassi di tag|Descrizione|
|----------|-----------|
|**&lt;c&gt;***testo*** &lt; /c&gt;**|Specifica che *testo* è codice. Questo tag può essere utilizzato dai generatori di documentazione per visualizzare il testo in un tipo di carattere appropriato per il codice.|
|**&lt;riepilogo&gt;***testo*** &lt; /summary&gt;**|Specifica che *testo* è una breve descrizione dell'elemento del programma. La descrizione è in genere una o due frasi.|
|**&lt;la sezione Osservazioni&gt;***testo*** &lt; /remarks&gt;**|Specifica che *testo* contiene informazioni aggiuntive sull'elemento del programma.|
|**&lt;param name = "***name***"&gt;***descrizione***&lt;/param&gt;**|Specifica il nome e una descrizione per un parametro di funzione o un metodo.|
|**&lt;typeparam name = "***name***"&gt;***descrizione***&lt;/typeparam&gt;**|Specifica il nome e una descrizione per un parametro di tipo.|
|**&lt;Restituisce&gt;***testo***&lt;/returns&gt;**|Specifica che *testo* descrive il valore restituito di una funzione o metodo.|
|**&lt;eccezione cref = "***tipo***"&gt;***descrizione***&lt;/exception&gt;**|Specifica il tipo di eccezione che può essere generato e le circostanze in cui viene generata un'eccezione.|
|**&lt;vedere cref = "***riferimento***"&gt;***testo*** &lt; /visualizzato&gt;**|Specifica un collegamento inline da un altro elemento del programma. Il *riferimento* è il nome, così come appare nel file di documentazione XML. Il *testo* è il testo visualizzato nel collegamento.|
|**&lt;seealso cref = "***riferimento***" /&gt;**|Specifica un collegamento Vedere anche la documentazione per un altro tipo. Il *riferimento* è il nome, così come appare nel file di documentazione XML. Vedere anche generalmente vengono visualizzati nella parte inferiore di una pagina della documentazione di collegamenti.|
|**&lt;para&gt;***testo***&lt;/para&gt;**|Specifica un paragrafo di testo. Viene utilizzato per separare il testo all'interno di **osservazioni** tag.|

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Di seguito è riportato un tipico commento della documentazione XML in un file della firma.

### <a name="code"></a>Codice

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Nell'esempio seguente viene illustrato il metodo alternativo, senza i tag XML. In questo esempio, l'intero testo del commento è considerato un riepilogo. Si noti che se non si specifica un tag di riepilogo in modo esplicito, è consigliabile non specificare altri tag, ad esempio **param** oppure **restituisce** tag.

### <a name="code"></a>Codice

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Opzioni del compilatore](compiler-options.md)
