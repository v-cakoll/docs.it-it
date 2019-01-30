---
title: Documentazione XML (F#)
description: Informazioni sul supporto in F# per la generazione di documentazione da commenti.
ms.date: 05/16/2016
ms.openlocfilehash: c5305dea8832112644710b2863269ef00feddd10
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204678"
---
# <a name="xml-documentation"></a>Documentazione di XML

È possibile produrre documentazione dai tripla barra (/ / /) commenti nel codice F#. Commenti in formato XML può precedere le dichiarazioni nel file di codice (. FS) o file di firma (. fsi).

## <a name="generating-documentation-from-comments"></a>Generazione di documentazione dai commenti

Il supporto in F# per la generazione di documentazione da commenti è uguale a quello in altri linguaggi .NET Framework. Come negli altri linguaggi .NET Framework, il [-l'opzione del compilatore doc](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) consente di produrre un file XML che contiene informazioni che è possibile convertire in documentazione con uno strumento, ad esempio [DocFX](https://dotnet.github.io/docfx/) o[ Sandcastle](https://github.com/EWSoftware/SHFB). La documentazione generata usando gli strumenti progettati per l'uso con gli assembly che vengono scritti in altri linguaggi .NET Framework in genere produce una visualizzazione delle API basata su form compilato dei F# costrutti di. A meno che non supportano in modo specifico gli strumenti di F#, la documentazione generata da questi strumenti non corrisponde la F# visualizzazione di un'API.

Per altre informazioni su come generare documentazione da XML, vedere [commenti in formato documentazione XML &#40;C&#35; Guida alla programmazione di&#41;](https://msdn.microsoft.com/library/b2s063f7).

## <a name="recommended-tags"></a>Tag consigliati

Esistono due modi per scrivere commenti in formato documentazione XML. Uno consiste nello scrivere semplicemente la documentazione direttamente in un commento con barra tripla, senza usare i tag XML. Se in questo caso, il testo del commento intero viene eseguito come documentazione di riepilogo per il costrutto di codice che segue immediatamente. Utilizzare questo metodo quando si desidera scrivere solo un breve riepilogo per ciascun costrutto. L'altro metodo consiste nell'utilizzare i tag XML per fornire più strutturata documentazione. Il secondo metodo consente di specificare note separate per un breve riepilogo, osservazioni aggiuntive, documentazione per ogni parametro e il parametro di tipo e le eccezioni generate e una descrizione del valore restituito. La tabella seguente descrive i tag XML che sono riconosciuti nella F# commenti al codice XML.

|Sintassi di tag|Descrizione|
|----------|-----------|
|**\<c\>**_text_**\</c\>**|Specifica che *testo* è codice. Questo tag può essere utilizzato dai generatori di documentazione per visualizzare il testo in un tipo di carattere appropriato per il codice.|
|**\<summary\>**_text_**\</summary\>**|Specifica che *testo* è una breve descrizione dell'elemento del programma. La descrizione è in genere una o due frasi.|
|**\<remarks\>**_text_**\</remarks\>**|Specifica che *testo* contiene informazioni aggiuntive sull'elemento del programma.|
|**\<param name="**_name_**"\>**_description_**\</param\>**|Specifica il nome e una descrizione per un parametro di funzione o un metodo.|
|**\<typeparam name="**_name_**"\>**_description_**\</typeparam\>**|Specifica il nome e una descrizione per un parametro di tipo.|
|**\<returns\>**_text_**\</returns\>**|Specifica che *testo* descrive il valore restituito di una funzione o metodo.|
|**\<exception cref="**_type_**"\>**_description_**\</exception\>**|Specifica il tipo di eccezione che può essere generato e le circostanze in cui viene generata un'eccezione.|
|**\<see cref="**_reference_**"\>**_text_**\</see\>**|Specifica un collegamento inline da un altro elemento del programma. Il *riferimento* è il nome, così come appare nel file di documentazione XML. Il *testo* è il testo visualizzato nel collegamento.|
|**\<seealso cref="**_reference_**"/\>**|Specifica un collegamento Vedere anche la documentazione per un altro tipo. Il *riferimento* è il nome, così come appare nel file di documentazione XML. Vedere anche generalmente vengono visualizzati nella parte inferiore di una pagina della documentazione di collegamenti.|
|**\<para\>**_text_**\</para\>**|Specifica un paragrafo di testo. Viene utilizzato per separare il testo all'interno di **osservazioni** tag.|

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
