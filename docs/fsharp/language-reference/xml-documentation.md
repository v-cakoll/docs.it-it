---
title: Documentazione XML
description: Informazioni sul supporto di F# per la generazione di documentazione dai commenti.
ms.date: 05/16/2016
ms.openlocfilehash: 0a87915c361fc88f0c05264e1c17278fd656a167
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344694"
---
# <a name="xml-documentation"></a>Documentazione XML

È possibile produrre documentazione dai commenti del codice a tre barre (///) F#in. I commenti XML possono precedere le dichiarazioni nei file di codice (. FS) o nei file di firma (. FSI).

## <a name="generating-documentation-from-comments"></a>Generazione della documentazione dai commenti

Il supporto di F# per la generazione di documentazione dai commenti è identico a quello di altri linguaggi .NET Framework. Come in altri linguaggi .NET Framework, l' [opzione del compilatore-doc](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) consente di produrre un file XML contenente informazioni che è possibile convertire nella documentazione usando uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB). La documentazione generata usando gli strumenti progettati per l'uso con gli assembly scritti in altri linguaggi di .NET Framework in genere produce una visualizzazione delle API basate sulla forma di F# costrutti compilata. A meno che gli strumenti F#non supportino in modo specifico, la documentazione generata F# da questi strumenti non corrisponde alla visualizzazione di un'API.

Per ulteriori informazioni su come generare documentazione da XML, vedere la [Guida&#41;alla programmazione &#40;di&#35; commenti in formato C](https://msdn.microsoft.com/library/b2s063f7)per la documentazione XML.

## <a name="recommended-tags"></a>Tag consigliati

Esistono due modi per scrivere commenti di documentazione XML. Uno è semplicemente scrivere la documentazione direttamente in un commento con una barra tripla, senza usare tag XML. In tal caso, l'intero testo del commento viene considerato come la documentazione riepilogativa del costrutto di codice che segue immediatamente. Utilizzare questo metodo quando si desidera scrivere solo un breve riepilogo per ogni costrutto. L'altro metodo consiste nell'usare i tag XML per fornire una documentazione più strutturata. Il secondo metodo consente di specificare note separate per un breve riepilogo, osservazioni aggiuntive, documentazione per ogni parametro e parametro di tipo ed eccezioni generate e una descrizione del valore restituito. Nella tabella seguente vengono descritti i tag XML riconosciuti F# nei commenti del codice XML.

|Sintassi Tag|Descrizione|
|----------|-----------|
|**\<c\>** _text_ **\</c\>**|Specifica che il *testo* è di codice. Questo tag può essere usato dai generatori di documentazione per visualizzare il testo in un tipo di carattere appropriato per il codice.|
|**\<summary\>** _text_ **\</summary\>**|Specifica che il *testo* è una breve descrizione dell'elemento del programma. La descrizione è in genere una o due frasi.|
|**\<remarks\>** _text_ **\</remarks\>**|Specifica che il *testo* contiene informazioni supplementari sull'elemento del programma.|
|**\<param name = "** _Name_ **"\>** _Description_ **\</param Returns\>**|Specifica il nome e la descrizione di una funzione o di un parametro del metodo.|
|**\<typeparam Name = "** _Name_ **"\>** _Description_ **\</typeparam\>**|Specifica il nome e la descrizione per un parametro di tipo.|
|**\<returns\>** _text_ **\</returns\>**|Specifica che il *testo* descrive il valore restituito di una funzione o di un metodo.|
|**\<Exception cref = "** _Type_ **"\>** _Description_ **\</Exception\>**|Specifica il tipo di eccezione che può essere generata e le circostanze in cui viene generata.|
|**\<vedere cref = "** _Reference_ **"\>** _Text_ **\</See\>**|Specifica un collegamento inline a un altro elemento del programma. Il *riferimento* è il nome che viene visualizzato nel file di documentazione XML. Il *testo* è il testo visualizzato nel collegamento.|
|**\<seealso cref = "** _reference_ **"/\>**|Specifica un collegamento vedere anche alla documentazione per un altro tipo. Il *riferimento* è il nome che viene visualizzato nel file di documentazione XML. Vedere anche i collegamenti vengono visualizzati in genere nella parte inferiore della pagina della documentazione.|
|**\<para\>** _text_ **\</para\>**|Specifica un paragrafo di testo. Viene usato per separare il testo all'interno del tag **Note** .|

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Di seguito è riportato un tipico commento della documentazione XML in un file di firma.

### <a name="code"></a>Codice

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Nell'esempio seguente viene illustrato il metodo alternativo senza tag XML. In questo esempio, l'intero testo del commento viene considerato un riepilogo. Si noti che se non si specifica in modo esplicito un tag di riepilogo, non è necessario specificare altri tag, ad esempio **param** o **Returns** .

### <a name="code"></a>Codice

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Opzioni del compilatore](compiler-options.md)
