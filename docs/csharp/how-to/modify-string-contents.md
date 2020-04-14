---
title: Come modificare il contenuto della stringa - Guida di C
ms.date: 02/26/2018
helpviewer_keywords:
- strings [C#], modifying
ms.openlocfilehash: f31fa94501ac2120e22e229dfc11babb8b8cc0f3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242855"
---
# <a name="how-to-modify-string-contents-in-c"></a>Come modificare il contenuto della stringa in CHow to modify string contents in C\#

Questo articolo illustra diverse tecniche per produrre un oggetto `string` modificando un oggetto `string` esistente. Tutte le tecniche illustrate restituiscono il risultato delle modifiche come nuovo oggetto `string`. Per maggior chiarezza, gli esempi archiviano il risultato in una nuova variabile. Quindi quando si esegue ogni esempio è possibile esaminare sia l'oggetto `string` originale che l'oggetto `string` derivante dalla modifica.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Questo articolo illustra diverse tecniche. È possibile sostituire il testo esistente. È possibile cercare criteri e sostituire il testo corrispondente ai criteri con altro testo. È possibile considerare una stringa come sequenza di caratteri. È anche possibile usare metodi pratici per la rimozione degli spazi. È consigliabile scegliere le tecniche più adatte allo scenario in cui si opera.

## <a name="replace-text"></a>Sostituire il testo

Il codice seguente crea una nuova stringa sostituendo il testo esistente con altro testo.

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#1)]

Il codice precedente illustra questa proprietà *non modificabile* delle stringhe. Come si vede nell'esempio precedente, la stringa originale, `source`, non viene modificata. Il metodo <xref:System.String.Replace%2A?displayProperty=nameWithType> crea un nuovo oggetto `string` contenente le modifiche.

Il metodo <xref:System.String.Replace%2A> può sostituire stringhe o caratteri singoli. In entrambi i casi, viene sostituita ogni ricorrenza del testo cercato.  Nell'esempio seguente tutte le sequenze di caratteri ' ' vengono sostituite da '\_':

[!code-csharp-interactive[replace characters](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#2)]

La stringa di origine non viene modificata e viene restituita una nuova stringa con la sostituzione.

## <a name="trim-white-space"></a>Eliminare gli spazi

È possibile usare i metodi <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType> e <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> per rimuovere tutti gli spazi iniziali o finali.  Il codice seguente visualizza un esempio con ogni metodo. La stringa di origine resta invariata e i metodi restituiscono una nuova stringa con il contenuto modificato.

[!code-csharp-interactive[trim white space](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#3)]

## <a name="remove-text"></a>Rimuovere il testo

È possibile rimuovere testo da una stringa usando il metodo <xref:System.String.Remove%2A?displayProperty=nameWithType>. Questo metodo rimuove un determinato numero di caratteri a partire da un indice specifico. Nell'esempio seguente viene illustrato come usare <xref:System.String.IndexOf%2A?displayProperty=nameWithType> seguito da <xref:System.String.Remove%2A> per rimuovere testo da una stringa:

[!code-csharp-interactive[remove text](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#4)]

## <a name="replace-matching-patterns"></a>Sostituire i criteri corrispondenti

È possibile usare le [espressioni regolari](../../standard/base-types/regular-expressions.md) per sostituire il testo corrispondente a determinati criteri con nuovo testo, che a sua volta può essere definito da un criterio. Nell'esempio seguente viene usata la classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> per trovare un criterio in una stringa di origine e sostituirlo con la combinazione corretta di maiuscole e minuscole. Il metodo <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> accetta una funzione che include tra i suoi argomenti la logica di sostituzione. In questo esempio la funzione (`LocalReplaceMatchCase`) è una **funzione locale** dichiarata all'interno del metodo di esempio. `LocalReplaceMatchCase` usa la classe <xref:System.Text.StringBuilder?displayProperty=nameWithType> per compilare la stringa di sostituzione con la combinazione corretta di maiuscole e minuscole.

Le espressioni regolari sono utili soprattutto per la ricerca e sostituzione di testo corrispondente a un criterio, anziché di testo noto. Per ulteriori informazioni, vedere [Come cercare stringhe.](search-strings.md) Il criterio di ricerca "the\s" cerca la parola "the" seguita da uno spazio. Tale parte del criterio garantisce che nella stringa di origine non venga rilevata la corrispondenza con "there". Per altre informazioni sugli elementi del linguaggio delle espressioni regolari, vedere [Linguaggio di espressioni regolari - Riferimento rapido](../../standard/base-types/regular-expression-language-quick-reference.md).

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#5)]

Il metodo <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> restituisce una stringa non modificabile con il contenuto dell'oggetto <xref:System.Text.StringBuilder>.

## <a name="modifying-individual-characters"></a>Modifica di caratteri singoli

È possibile produrre una matrice di caratteri da una stringa, modificare il contenuto della matrice e quindi creare una nuova stringa dal contenuto modificato della matrice.

Nell'esempio seguente viene illustrato come sostituire un gruppo di caratteri in una stringa. In primo luogo si usa il metodo <xref:System.String.ToCharArray?displayProperty=nameWithType> per creare una matrice di caratteri. Il metodo <xref:System.String.IndexOf%2A> viene usato per trovare l'indice iniziale della parola "fox". I tre caratteri successivi vengono sostituiti con una parola diversa. Infine viene creata una nuova stringa dalla matrice di caratteri aggiornata.

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#6)]

## <a name="programmatically-build-up-string-content"></a>Compilazione di contenuto di stringhe a livello di codiceProgrammatically build up string content

Poiché le stringhe non sono modificabili, negli esempi precedenti vengono tutti create stringhe temporanee o matrici di caratteri. Negli scenari ad alte prestazioni, può essere opportuno evitare queste allocazioni di heap. .NET Core <xref:System.String.Create%2A?displayProperty=nameWithType> fornisce un metodo che consente di compilare a livello di codice il contenuto del carattere di una stringa tramite un callback evitando le allocazioni di stringhe temporanee intermedie.

[!code-csharp[using string.Create to programmatically build the string content for a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#7)]

È possibile modificare una stringa in un blocco fisso con codice unsafe, ma è **consigliabile** modificare il contenuto della stringa dopo la creazione di una stringa. In questo modo si romperanno le cose in modi imprevedibili. Ad esempio, se qualcuno stagna una stringa che ha lo stesso contenuto del tuo, otterrà la tua copia e non si aspetta che tu stia modificando la sua stringa.

È possibile provare questi esempi esaminando il codice nel repository [GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings). Oppure è possibile scaricare gli esempi [come file ZIP](../../../samples/snippets/csharp/how-to/strings.zip).

## <a name="see-also"></a>Vedere anche

- [Espressioni regolari di .NET Framework](../../standard/base-types/regular-expressions.md)
- [Linguaggio di espressioni regolari - Riferimento rapido](../../standard/base-types/regular-expression-language-quick-reference.md)
