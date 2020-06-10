---
title: Come modificare il contenuto di una stringa-Guida a C#
ms.date: 02/26/2018
helpviewer_keywords:
- strings [C#], modifying
ms.openlocfilehash: a32665b67cfa73aa7d4753a1427c6955827e1b86
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84663005"
---
# <a name="how-to-modify-string-contents-in-c"></a>Come modificare il contenuto di una stringa in C\#

Questo articolo illustra diverse tecniche per produrre un oggetto `string` modificando un oggetto `string` esistente. Tutte le tecniche illustrate restituiscono il risultato delle modifiche come nuovo oggetto `string`. Per maggior chiarezza, gli esempi archiviano il risultato in una nuova variabile. Quindi quando si esegue ogni esempio è possibile esaminare sia l'oggetto `string` originale che l'oggetto `string` derivante dalla modifica.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Questo articolo illustra diverse tecniche. È possibile sostituire il testo esistente. È possibile cercare criteri e sostituire il testo corrispondente ai criteri con altro testo. È possibile considerare una stringa come sequenza di caratteri. È anche possibile usare metodi pratici per la rimozione degli spazi. Scegliere le tecniche più simili a quelle dello scenario.

## <a name="replace-text"></a>Sostituire il testo

Il codice seguente crea una nuova stringa sostituendo il testo esistente con altro testo.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet1":::

Il codice precedente illustra questa proprietà *non modificabile* delle stringhe. Come si vede nell'esempio precedente, la stringa originale, `source`, non viene modificata. Il metodo <xref:System.String.Replace%2A?displayProperty=nameWithType> crea un nuovo oggetto `string` contenente le modifiche.

Il metodo <xref:System.String.Replace%2A> può sostituire stringhe o caratteri singoli. In entrambi i casi, viene sostituita ogni ricorrenza del testo cercato.  Nell'esempio seguente tutte le sequenze di caratteri ' ' vengono sostituite da '\_':

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet2":::

La stringa di origine non viene modificata e viene restituita una nuova stringa con la sostituzione.

## <a name="trim-white-space"></a>Eliminare gli spazi

È possibile usare i metodi <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType> e <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> per rimuovere tutti gli spazi iniziali o finali.  Il codice seguente visualizza un esempio con ogni metodo. La stringa di origine resta invariata e i metodi restituiscono una nuova stringa con il contenuto modificato.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet3":::

## <a name="remove-text"></a>Rimuovere il testo

È possibile rimuovere testo da una stringa usando il metodo <xref:System.String.Remove%2A?displayProperty=nameWithType>. Questo metodo rimuove un determinato numero di caratteri a partire da un indice specifico. Nell'esempio seguente viene illustrato come usare <xref:System.String.IndexOf%2A?displayProperty=nameWithType> seguito da <xref:System.String.Remove%2A> per rimuovere testo da una stringa:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet4":::

## <a name="replace-matching-patterns"></a>Sostituire i criteri corrispondenti

È possibile usare le [espressioni regolari](../../standard/base-types/regular-expressions.md) per sostituire il testo corrispondente a determinati criteri con nuovo testo, che a sua volta può essere definito da un criterio. Nell'esempio seguente viene usata la classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> per trovare un criterio in una stringa di origine e sostituirlo con la combinazione corretta di maiuscole e minuscole. Il metodo <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> accetta una funzione che include tra i suoi argomenti la logica di sostituzione. In questo esempio la funzione (`LocalReplaceMatchCase`) è una **funzione locale** dichiarata all'interno del metodo di esempio. `LocalReplaceMatchCase` usa la classe <xref:System.Text.StringBuilder?displayProperty=nameWithType> per compilare la stringa di sostituzione con la combinazione corretta di maiuscole e minuscole.

Le espressioni regolari sono utili soprattutto per la ricerca e sostituzione di testo corrispondente a un criterio, anziché di testo noto. Per ulteriori informazioni, vedere [come eseguire la ricerca di stringhe](search-strings.md). Il criterio di ricerca "the\s" cerca la parola "the" seguita da uno spazio. Tale parte del criterio garantisce che nella stringa di origine non venga rilevata la corrispondenza con "there". Per altre informazioni sugli elementi del linguaggio delle espressioni regolari, vedere [Linguaggio di espressioni regolari - Riferimento rapido](../../standard/base-types/regular-expression-language-quick-reference.md).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet5":::

Il metodo <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> restituisce una stringa non modificabile con il contenuto dell'oggetto <xref:System.Text.StringBuilder>.

## <a name="modifying-individual-characters"></a>Modifica di caratteri singoli

È possibile produrre una matrice di caratteri da una stringa, modificare il contenuto della matrice e quindi creare una nuova stringa dal contenuto modificato della matrice.

Nell'esempio seguente viene illustrato come sostituire un gruppo di caratteri in una stringa. In primo luogo si usa il metodo <xref:System.String.ToCharArray?displayProperty=nameWithType> per creare una matrice di caratteri. Il metodo <xref:System.String.IndexOf%2A> viene usato per trovare l'indice iniziale della parola "fox". I tre caratteri successivi vengono sostituiti con una parola diversa. Infine viene creata una nuova stringa dalla matrice di caratteri aggiornata.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet6":::

## <a name="programmatically-build-up-string-content"></a>Compilare contenuto stringa a livello di codice

Poiché le stringhe non sono modificabili, negli esempi precedenti vengono create stringhe temporanee o matrici di caratteri. Negli scenari a prestazioni elevate può essere utile evitare queste allocazioni di heap. .NET Core fornisce un <xref:System.String.Create%2A?displayProperty=nameWithType> metodo che consente di compilare a livello di codice il contenuto di una stringa tramite un callback, evitando al tempo stesso le allocazioni di stringhe temporanee intermedie.

:::code language="csharp" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet7":::

È possibile modificare una stringa in un blocco fisso con codice non sicuro, ma è **fortemente** sconsigliata modificare il contenuto della stringa dopo la creazione di una stringa. In questo modo si interrompono le operazioni in modi imprevedibili. Se, ad esempio, un utente centralizza una stringa con lo stesso contenuto, otterrà la copia e non si aspetta che la stringa venga modificata.

## <a name="see-also"></a>Vedere anche

- [.NET Framework espressioni regolari](../../standard/base-types/regular-expressions.md)
- [Linguaggio di espressioni regolari-riferimento rapido](../../standard/base-types/regular-expression-language-quick-reference.md)
