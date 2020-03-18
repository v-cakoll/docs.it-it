---
title: Come confrontare le stringhe - Guida di C
description: Informazioni su come confrontare e ordinare i valori stringa, con o senza maiuscole, con o senza ordinamento specifico delle impostazioni cultura
ms.date: 10/03/2018
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.openlocfilehash: dda3ec8cb6a0131867e6ea3bb0cf7199d86058ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73973330"
---
# <a name="how-to-compare-strings-in-c"></a>Come confrontare stringhe in C\#

Il confronto delle stringhe viene eseguito per rispondere a una delle due domande seguenti: "Queste due stringhe sono uguali?" oppure "In che ordine vengono disposte queste stringhe quando si esegue l'ordinamento?"

Queste due domande vengono complicate da fattori propri dei confronti fra stringhe:

- È possibile scegliere un confronto ordinale o linguistico.
- È possibile scegliere se la distinzione maiuscole/minuscole è importante.
- È possibile scegliere confronti specifici in base alle impostazioni cultura.
- I confronti linguistici dipendono dalle impostazioni cultura e dalla piattaforma.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Quando si confrontano le stringhe, si definisce un ordine tra di esse. I confronti vengono usati per ordinare una sequenza di stringhe. Quando la sequenza è disposta in un ordine noto, l'esecuzione di una ricerca risulta più semplice sia per gli utenti che per le applicazioni. Altri confronti possono verificare se le stringhe sono uguali. Questi controlli di similitudine sono simili alla verifica di uguaglianza, ma è possibile che alcune differenze, quali le maiuscole/minuscole, vengano ignorate.

## <a name="default-ordinal-comparisons"></a>Confronti ordinali predefiniti

Per impostazione predefinita, le operazioni più comuni:

- <xref:System.String.CompareTo%2A?displayProperty=nameWithType>
- <xref:System.String.Equals%2A?displayProperty=nameWithType>
- <xref:System.String.op_Equality%2A?displayProperty=nameWithType>e <xref:System.String.op_Inequality%2A?displayProperty=nameWithType>, ovvero gli operatori [ `==` `!=` ](../language-reference/operators/equality-operators.md#string-equality)di uguaglianza e , rispettivamente

eseguire un confronto ordinale con distinzione tra maiuscole e minuscole e, se necessario, utilizzare le impostazioni cultura correnti. Nell'esempio seguente viene illustrato che:The following example demonstrates that:

[!code-csharp-interactive[Comparing strings using an ordinal comparison](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#1)]

Il confronto ordinale predefinito non prende in considerazione le regole linguistiche quando si confrontano le stringhe. ma viene confrontato il valore binario di ogni oggetto <xref:System.Char> nelle due stringhe. Di conseguenza, anche il confronto ordinale predefinito prevede la distinzione tra maiuscole e minuscole.

Si noti che <xref:System.String.Equals%2A?displayProperty=nameWithType> il `==` test `!=` di uguaglianza con <xref:System.String.CompareTo%2A?displayProperty=nameWithType> e <xref:System.String.Compare(System.String,System.String)?displayProperty=nameWithType)> gli operatori e differisce dal confronto tra stringhe utilizzando i metodi e . Mentre i test di uguaglianza eseguono un confronto ordinale con distinzione tra maiuscole e minuscole, i metodi di confronto eseguono un confronto tra maiuscole e minuscole e dipendenti dalle impostazioni cultura utilizzando le impostazioni cultura correnti. Dato che i metodi di confronto predefiniti spesso eseguono diversi tipi di confronti, è consigliabile chiarire sempre l'intento del codice chiamando un overload che specifichi in modo esplicito il tipo di confronto da eseguire.

## <a name="case-insensitive-ordinal-comparisons"></a>Confronti ordinali senza distinzione tra maiuscole e minuscole

Il metodo <xref:System.String.Equals(System.String,System.StringComparison)?displayProperty=nameWithType> consente di specificare un valore <xref:System.StringComparison> pari a <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType>
per un confronto ordinale senza distinzione tra maiuscole e minuscole. È anche disponibile un metodo <xref:System.String.Compare(System.String,System.String,System.StringComparison)?displayProperty=nameWithType> statico che esegue un confronto ordinale senza distinzione tra maiuscole e minuscole, se si specifica il valore <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> per l'argomento <xref:System.StringComparison>. Questi metodi sono illustrati nella figura seguente.

[!code-csharp-interactive[Comparing strings ignoring case](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#2)]

Quando si esegue un confronto ordinale senza distinzione tra maiuscole e minuscole, questi metodi usano le convenzioni di combinazione di maiuscole e minuscole delle [impostazioni cultura inglese non dipendenti da paese/area geografica](xref:System.Globalization.CultureInfo.InvariantCulture).

## <a name="linguistic-comparisons"></a>Confronti linguistici

Le stringhe possono anche essere ordinate in base alle regole linguistiche delle impostazioni cultura correnti.
Questo ordinamento è detto anche "ordinamento di Word". Quando si esegue un confronto linguistico, è possibile che a determinati caratteri Unicode non alfanumerici venga assegnata una valenza specifica. Ad esempio il trattino "-" può avere una valenza ridotta, pertanto le parole "co-op"e "coop" vengono visualizzate l'una accanto all'altra nell'ordinamento. Alcuni caratteri Unicode possono anche essere equivalenti a una sequenza di istanze di <xref:System.Char>. L'esempio seguente usa la frase "Ballano per strada." in tedesco con "ss" (U+0073 U+0073) in una stringa e 'ß' (U+00DF) in un'altra. Dal punto di vista linguistico (in Windows), "ss" equivale al carattere tedesco Esszet "ß", sia nelle impostazioni cultura "en-US" che in quelle "de-DE".

[!code-csharp-interactive[Comparing strings using linguistic rules](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#3)]

Questo esempio dimostra che i confronti linguistici sono dipendenti dal sistema operativo. L'host della finestra interattiva è un host Linux. Il confronto linguistico e il confronto ordinale producono gli stessi risultati. Se si esegue lo stesso esempio in un host Windows viene visualizzato l'output seguente:

```console
<coop> is less than <co-op> using invariant culture
<coop> is greater than <co-op> using ordinal comparison
<coop> is less than <cop> using invariant culture
<coop> is less than <cop> using ordinal comparison
<co-op> is less than <cop> using invariant culture
<co-op> is less than <cop> using ordinal comparison
```

In Windows, l'ordinamento di "cop", "coop" e "co-op" cambia quando si passa da un confronto linguistico a un confronto ordinale. Anche l'ordinamento delle due frasi in tedesco cambia a seconda del tipo di confronto.

## <a name="comparisons-using-specific-cultures"></a>Confronti che usano impostazioni cultura specifiche

Questo esempio archivia oggetti <xref:System.Globalization.CultureInfo> per le impostazioni cultura en-US e de-DE.
I confronti vengono eseguiti usando un oggetto <xref:System.Globalization.CultureInfo> per garantire un confronto dipendente dalle impostazioni cultura.

Le impostazioni cultura usate hanno effetto sui confronti linguistici. L'esempio seguente visualizza i risultati del confronto tra le due frasi in lingua tedesca usando le impostazioni cultura "en-US" e le impostazioni cultura "de-DE":

[!code-csharp-interactive[Comparing strings across cultures](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#4)]

In genere i confronti con rilevamento delle impostazioni cultura vengono usati per confrontare e ordinare stringhe immesse dagli utenti. I caratteri e le convenzioni di ordinamento di queste stringhe possono variare a seconda delle impostazioni locali del computer dell'utente. Anche stringhe che contengono caratteri identici potrebbero essere ordinate in modo diverso a seconda delle impostazioni cultura del thread corrente. Provare ad eseguire questo codice di esempio anche in locale, in un computer Windows. Si ottengono i risultati seguenti:

```console
<coop> is less than <co-op> using en-US culture
<coop> is greater than <co-op> using ordinal comparison
<coop> is less than <cop> using en-US culture
<coop> is less than <cop> using ordinal comparison
<co-op> is less than <cop> using en-US culture
<co-op> is less than <cop> using ordinal comparison
```

I confronti linguistici dipendono dalle impostazioni cultura correnti e dal sistema operativo. Tenere presente questo aspetto quando si lavora con confronti tra stringhe.

## <a name="linguistic-sorting-and-searching-strings-in-arrays"></a>Ordinamento linguistico e ricerca di stringhe nelle matrici

Gli esempi seguenti illustrano come eseguire l'ordinamento e la ricerca di stringhe in una matrice mediante un confronto linguistico dipendente dalle impostazioni cultura correnti. Si usano i metodi <xref:System.Array> statici che accettano un parametro <xref:System.StringComparer?displayProperty=nameWithType>.

Questo esempio illustra come ordinare una matrice di stringhe in base alle impostazioni cultura correnti:

[!code-csharp-interactive[Sorting an array of strings](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#5)]

Quando la matrice è ordinata, è possibile cercare voci con una ricerca binaria. Una ricerca binaria inizia a metà della raccolta per determinare quale metà contiene la stringa cercata. Ogni confronto successivo divide a metà la parte rimanente della raccolta.  La matrice viene ordinata usando <xref:System.StringComparer.CurrentCulture?displayProperty=nameWithType>. La funzione locale `ShowWhere` visualizza informazioni sul punto in cui è stata trovata la stringa. Se la stringa non viene trovata, il valore restituito indica quale sarebbe la sua posizione se fosse stata trovata.

[!code-csharp-interactive[Searching in a sorted array](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#6)]

## <a name="ordinal-sorting-and-searching-in-collections"></a>Ordinamento e ricerca ordinali nelle raccolte

Il codice seguente usa la classe della raccolta <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> per memorizzare le stringhe. Le stringhe vengono ordinate usando il metodo <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>. Questo metodo richiede un delegato che confronta e ordina due stringhe. La funzione di confronto è resa disponibile dal metodo <xref:System.String.CompareTo%2A?displayProperty=nameWithType>. Eseguire l'esempio e osservare l'ordine. Questa operazione di ordinamento usa un ordinamento ordinale con distinzione tra maiuscole e minuscole. Per specificare regole di confronto diverse sarebbe necessario usare i metodi <xref:System.String.Compare%2A?displayProperty=nameWithType> statici.

[!code-csharp-interactive[Sorting a list of strings](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#7)]

Dopo l'ordinamento è possibile eseguire ricerche nell'elenco di stringhe usando una ricerca binaria. L'esempio seguente illustra come eseguire una ricerca nell'elenco ordinato usando la stessa funzione di confronto. La funzione locale `ShowWhere` visualizza il punto in cui si trova o dovrebbe trovarsi il testo cercato:

[!code-csharp-interactive[csProgGuideStrings#11](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#8)]

Assicurarsi di usare sempre lo stesso tipo di confronto per l'ordinamento e la ricerca. L'uso di tipi di confronto diversi per l'ordinamento e la ricerca produce risultati imprevisti.

Le classi Collection, ad esempio <xref:System.Collections.Hashtable?displayProperty=nameWithType>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>, e <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> contengono costruttori che accettano un parametro <xref:System.StringComparer?displayProperty=nameWithType> quando il tipo degli elementi o delle chiavi è `string`. In generale è necessario usare sempre questi costruttori, quando possibile, e specificare il parametro <xref:System.StringComparer.Ordinal?displayProperty=nameWithType> o <xref:System.StringComparer.OrdinalIgnoreCase?displayProperty=nameWithType>.

## <a name="reference-equality-and-string-interning"></a>Uguaglianza di riferimenti e centralizzazione delle stringhe.

<xref:System.Object.ReferenceEquals%2A> non è stato usato in nessun esempio. Questo metodo determina se due stringhe sono lo stesso oggetto. Questo può causare risultati incoerenti nei confronti tra stringhe. L'esempio seguente illustra la funzionalità di *centralizzazione delle stringhe* di C#. Quando un programma dichiara due o più variabili di stringa identiche, il compilatore le archivia tutte nello stesso percorso. Chiamando il metodo <xref:System.Object.ReferenceEquals%2A> è possibile vedere che le due stringhe si riferiscono effettivamente allo stesso oggetto in memoria. Per evitare la centralizzazione, usare il metodo <xref:System.String.Copy%2A?displayProperty=nameWithType>. Dopo la copia, le due stringhe hanno posizioni di archiviazione diverse anche se hanno lo stesso valore. Eseguire l'esempio seguente per verificare che le stringhe `a` e `b` sono *centralizzate*, ovvero condividono la stessa risorsa di archiviazione. Le stringhe `a` e `c` non lo sono.

[!code-csharp-interactive[Demonstrating string interning](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#9)]

> [!NOTE]
> Per verificare l'uguaglianza fra stringhe è opportuno usare metodi che consentono di specificare in modo esplicito il tipo di confronto da eseguire. In questo modo il codice risulta molto più gestibile e leggibile. Usare gli overload dei metodi delle classi <xref:System.String?displayProperty=nameWithType> e <xref:System.Array?displayProperty=nameWithType> che accettano un parametro di enumerazione <xref:System.StringComparison>. È possibile specificare il tipo di confronto da eseguire. Evitare di usare gli operatori `==` e `!=` nelle verifiche di uguaglianza. I metodi di istanza <xref:System.String.CompareTo%2A?displayProperty=nameWithType> eseguono sempre un confronto ordinale con distinzione tra maiuscole e minuscole. Sono adatti soprattutto per ordinare le stringhe in ordine alfabetico.

È possibile inserire una stringa nel pool interno oppure recuperare un riferimento a una stringa inserita nel pool interno chiamando il metodo <xref:System.String.Intern%2A?displayProperty=nameWithType>. Per determinare se una stringa è inserita nel pool interno, chiamare il metodo <xref:System.String.IsInterned%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- [Stringhe](../programming-guide/strings/index.md)
- [Confronto di stringhe](../../standard/base-types/comparing.md)
- [Globalizzazione e localizzazione di applicazioni](/visualstudio/ide/globalizing-and-localizing-applications)
