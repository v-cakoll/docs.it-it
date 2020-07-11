---
title: Stringhe - Guida per programmatori C#
ms.date: 06/27/2019
helpviewer_keywords:
- C# language, strings
- strings [C#]
ms.assetid: 21580405-cb25-4541-89d5-037846a38b07
ms.openlocfilehash: 7bf5cba51a2e72d3a648f795f018220a452e51f5
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226595"
---
# <a name="strings-c-programming-guide"></a>Stringhe (Guida per programmatori C#)
Una stringa è un oggetto di tipo <xref:System.String> il cui valore è testo. Internamente il testo viene archiviato come una raccolta di sola lettura sequenziale di oggetti <xref:System.Char>. Le stringhe C# non presentano un carattere di terminazione null alla fine, pertanto una stringa C# può contenere qualsiasi numero di caratteri null incorporati ('\0'). La proprietà <xref:System.String.Length%2A> di una stringa rappresenta il numero di oggetti `Char` in essa contenuti e non il numero di caratteri Unicode. Per accedere ai singoli punti di codice Unicode in una stringa usare l'oggetto <xref:System.Globalization.StringInfo>.  
  
## <a name="string-vs-systemstring"></a>stringa e System. String  
 In Visual Basic la parola chiave `string` è un alias per <xref:System.String>. `String` e `string` sono pertanto equivalenti ed è possibile usare la convenzione di denominazione che si preferisce. La classe `String` fornisce molti metodi per creare, modificare e confrontare stringhe in modo sicuro. Inoltre, il linguaggio C# esegue l'overload di alcuni operatori per semplificare le operazioni comuni sulle stringhe. Per altre informazioni sull'uso della parola chiave, vedere [string](../../language-reference/builtin-types/reference-types.md). Per altre informazioni sul tipo e sui relativi metodi, vedere <xref:System.String>.  
  
## <a name="declaring-and-initializing-strings"></a>Dichiarazione e inizializzazione di stringhe  
 È possibile dichiarare e inizializzare stringhe in vari modi, come mostrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStrings#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#1)]  
  
 Si noti che l'operatore [new](../../language-reference/operators/new-operator.md) non viene usato per creare un oggetto stringa tranne nel caso in cui la stringa viene inizializzata con una matrice di caratteri.  
  
 Inizializzare una stringa con il valore costante <xref:System.String.Empty> per creare un nuovo oggetto <xref:System.String> con stringa di lunghezza zero. La rappresentazione del valore letterale stringa di una stringa di lunghezza zero è "". L'inizializzazione di stringhe con il valore <xref:System.String.Empty> anziché con [null](../../language-reference/keywords/null.md) riduce le probabilità di un errore <xref:System.NullReferenceException>. Usare il metodo statico <xref:System.String.IsNullOrEmpty%28System.String%29> per verificare il valore di una stringa prima di provare ad accedere alla stringa.  
  
## <a name="immutability-of-string-objects"></a>Immutabilità degli oggetti stringa  
 Gli oggetti stringa sono *immutabili*, ovvero non possono essere modificati una volta creati. Tutti i metodi <xref:System.String> e gli operatori C# che sembrano modificare una stringa in realtà restituiscono i risultati in un nuovo oggetto stringa. Nell'esempio seguente, quando il contenuto di `s1` e `s2` viene concatenato per formare un'unica stringa, le due stringhe originali restano immutate. L'operatore `+=` crea una nuova stringa che contiene il contenuto delle due stringhe combinato. Il nuovo oggetto viene assegnato alla variabile `s1` e l'oggetto originale assegnato a `s1` viene rilasciato per l'operazione di Garbage Collection perché nessun'altra variabile contiene un riferimento a tale oggetto.  
  
 [!code-csharp[csProgGuideStrings#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#2)]  
  
 Dato che una "modifica" della stringa è in effetti la creazione di una nuova stringa, è necessario prestare attenzione quando si creano riferimenti alle stringhe. Se si crea un riferimento a una stringa e quindi si "modifica" la stringa originale, il riferimento continuerà a puntare all'oggetto originale anziché al nuovo oggetto creato quando la stringa è stata modificata. Il codice seguente illustra questo comportamento:  
  
 [!code-csharp[csProgGuideStrings#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#25)]  
  
 Per ulteriori informazioni su come creare nuove stringhe basate su modifiche come le operazioni di ricerca e sostituzione sulla stringa originale, vedere [come modificare il contenuto di una stringa](../../how-to/modify-string-contents.md).  
  
## <a name="regular-and-verbatim-string-literals"></a>Valori letterali stringa normali e verbatim  
 Usare valori letterali stringa normali quando è necessario incorporare caratteri di escape forniti da C#, come mostrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStrings#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#3)]  
  
 Usare stringhe verbatim per praticità e migliore leggibilità quando il testo della stringa contiene barre rovesciate, ad esempio nei percorsi di file. Dato che le stringhe verbatim mantengono i caratteri di nuova riga come parte del testo della stringa, possono essere usate per inizializzare stringhe su più righe. Usare virgolette doppie per incorporare una virgoletta in una stringa verbatim. L'esempio seguente mostra alcuni usi comuni delle stringhe verbatim:  
  
 [!code-csharp[csProgGuideStrings#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#4)]  
  
## <a name="string-escape-sequences"></a>Sequenze di escape delle stringhe  
  
|Sequenza di escape|Nome carattere|Codifica Unicode|  
|---------------------|--------------------|----------------------|  
|\\'|Virgoletta singola|0x0027|  
|\\"|Virgoletta doppia|0x0022|  
|\\\\ |Barra rovesciata|0x005C|  
|\0|Null|0x0000|  
|\a|Avviso|0x0007|  
|\b|Backspace|0x0008|  
|\f|Avanzamento carta|0x000C|  
|\n|Nuova riga|0x000A|  
|\r|Ritorno a capo|0x000D|  
|\t|Tabulazione orizzontale|0x0009|  
|\v|Tabulazione verticale|0x000B|  
|\u|Sequenza di escape Unicode (UTF-16)|`\uHHHH`(intervallo: 0000-FFFF; esempio: `\u00E7` = "ç")|  
|\U|Sequenza di escape Unicode (UTF-32)|`\U00HHHHHH`(intervallo: 000000-10FFFF; esempio: `\U0001F47D` = "& # x1F47D;")|  
|\x|Sequenza di escape Unicode simile a "\u", ma con lunghezza variabile|`\xH[H][H][H]`(intervallo: 0-FFFF; esempio: `\x00E7` o `\x0E7` o `\xE7` = "ç")|  
  
> [!WARNING]
> Quando si usa la sequenza di escape `\x` e si specificano meno di 4 cifre esadecimali, se i caratteri immediatamente seguenti la sequenza di escape sono cifre esadecimali valide (ad esempio 0-9, A-F e a-f), questi verranno interpretati come parte della sequenza di escape. Ad esempio, `\xA1` produce "&#161;" che è il punto di codice U+00A1. Se tuttavia il carattere successivo è "A" oppure "a", la sequenza di escape verrà invece interpretata come `\xA1A` e produrrà "&#x0A1A;" che è il punto di codice U+0A1A. In questi casi, specificando tutte e 4 le cifre esadecimali (ad esempio, `\x00A1`) si eviteranno possibili interpretazioni errate.  
  
> [!NOTE]
> In fase di compilazione, le stringhe verbatim vengono convertite in stringhe normali con tutte le stesse sequenze di escape. Pertanto, se si visualizza una stringa verbatim nella finestra Espressioni di controllo del debugger, si vedranno i caratteri di escape aggiunti dal compilatore e non la versione verbatim del codice sorgente. Ad esempio, la stringa verbatim `@"C:\files.txt"` verrà visualizzata nella finestra delle espressioni di controllo come "C \\\files.txt".  
  
## <a name="format-strings"></a>Stringhe di formato  
 Una stringa di formato è una stringa il cui contenuto viene determinato dinamicamente in fase di esecuzione. Le stringhe di formato vengono create incorporando segnaposto o *espressioni interpolate* all'interno di parentesi graffe in una stringa. Tutti gli elementi all'interno delle parentesi graffe (`{...}`) restituiranno un valore e verranno visualizzati come stringa formattata in fase di esecuzione. Esistono due metodi per creare stringhe di formato: interpolazione di stringhe e formattazione composita.

### <a name="string-interpolation"></a>Interpolazione di stringhe
Le [*stringhe interpolate*](../../language-reference/tokens/interpolated.md), disponibili in C# 6.0 e versioni successive, vengono identificate dal carattere speciale `$` e includono le espressioni interpolate tra parentesi graffe. Se non si ha familiarità con l'interpolazione di stringhe, vedere l'[esercitazione interattiva Interpolazione di stringhe - C#](../../tutorials/exploration/interpolated-strings.yml) per una veloce panoramica.

Usare l'interpolazione di stringhe per migliorare la leggibilità e la gestibilità del codice. L'interpolazione di stringhe permette di ottenere gli stessi risultati del metodo `String.Format`, ma è più facile da usare e migliora la chiarezza inline.

[!code-csharp[csProgGuideFormatStrings](~/samples/snippets/csharp/programming-guide/strings/Strings_1.cs#StringInterpolation)]

### <a name="composite-formatting"></a>Formattazione composita
<xref:System.String.Format%2A?displayProperty=nameWithType> utilizza segnaposto tra parentesi graffe per creare una stringa di formato. Questo esempio restituisce un output simile a quello del metodo di interpolazione di stringhe usato sopra.
  
[!code-csharp[csProgGuideFormatStrings](~/samples/snippets/csharp/programming-guide/strings/Strings_1.cs#StringFormat)]

Per altre informazioni sulla formattazione dei tipi .NET, vedere [Formattazione di tipi in .NET](../../../standard/base-types/formatting-types.md).
  
## <a name="substrings"></a>Sottostringhe  
 Una sottostringa è qualsiasi sequenza di caratteri contenuta in una stringa. Usare il metodo <xref:System.String.Substring%2A> per creare una nuova stringa da una parte della stringa originale. È possibile cercare una o più occorrenze di una sottostringa tramite il metodo <xref:System.String.IndexOf%2A>. Usare il metodo <xref:System.String.Replace%2A> per sostituire tutte le occorrenze di una sottostringa specificata con una nuova stringa. Come il metodo <xref:System.String.Substring%2A>, anche <xref:System.String.Replace%2A> restituisce una nuova stringa e non modifica la stringa originale. Per ulteriori informazioni, vedere [come](../../how-to/search-strings.md) eseguire la ricerca di stringhe e [come modificare il contenuto](../../how-to/modify-string-contents.md)di una stringa.
  
 [!code-csharp[csProgGuideStrings#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#7)]  
  
## <a name="accessing-individual-characters"></a>Accesso a caratteri singoli  
 È possibile utilizzare la notazione di matrice con un valore di indice per ottenere l'accesso in sola lettura a singoli caratteri, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStrings#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#8)]  
  
 Se i metodi <xref:System.String> non specificano la funzionalità richiesta per modificare singoli caratteri in una stringa, è possibile usare un oggetto <xref:System.Text.StringBuilder> per modificare i singoli caratteri "sul posto", quindi creare una nuova stringa per archiviare i risultati tramite i metodi <xref:System.Text.StringBuilder>. Nell'esempio seguente presupporre che sia necessario modificare la stringa originale in un modo specifico e archiviare quindi i risultati per uso futuro:  
  
 [!code-csharp[csProgGuideStrings#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#27)]  
  
## <a name="null-strings-and-empty-strings"></a>Stringhe null e stringhe vuote  
 Una stringa vuota è un'istanza di un oggetto <xref:System.String?displayProperty=nameWithType> che contiene zero caratteri. Le stringhe vuote sono utilizzate di frequente in diversi scenari di programmazione per rappresentare un campo di testo vuoto. È possibile chiamare metodi su stringhe vuote, perché sono oggetti <xref:System.String?displayProperty=nameWithType> validi. Le stringhe vuote vengono inizializzate come indicato di seguito:  
  
```csharp  
string s = String.Empty;  
```  
  
 Al contrario una stringa null non fa riferimento a un'istanza di un oggetto <xref:System.String?displayProperty=nameWithType> e qualsiasi chiamata di un metodo su una stringa null causa un'eccezione <xref:System.NullReferenceException>. È tuttavia possibile usare stringhe null nelle operazioni di concatenazione e confronto con altre stringhe. Gli esempi seguenti illustrano alcuni casi in cui un riferimento a una stringa null causa o meno la generazione di un'eccezione:  
  
 [!code-csharp[csProgGuideStrings#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#20)]  
  
## <a name="using-stringbuilder-for-fast-string-creation"></a>Uso di StringBuilder per la creazione veloce di stringhe  
 Le operazioni sulle stringhe in .NET sono altamente ottimizzate e nella maggior parte dei casi non influiscono sulle prestazioni in modo significativo. Tuttavia, in alcuni scenari, ad esempio cicli rigidi eseguiti molte centinaia o migliaia di volte, le operazioni sulle stringhe possono incidere sulle prestazioni. La classe <xref:System.Text.StringBuilder> crea un buffer di stringhe che offre prestazioni migliori se il programma esegue numerose modifiche di stringhe. La stringa <xref:System.Text.StringBuilder> consente anche di riassegnare singoli caratteri, un'operazione non supportata dal tipo di dati string incorporato. Questo codice, ad esempio, consente di modificare il contenuto di una stringa senza crearne una nuova:  
  
 [!code-csharp[csProgGuideStrings#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#15)]  
  
 In questo esempio viene usato un oggetto <xref:System.Text.StringBuilder> per creare una stringa da un set di tipi numerici:  
  
 [!code-csharp[TestStringBuilder#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/TestStringBuilder.cs)]
  
## <a name="strings-extension-methods-and-linq"></a>Stringhe, metodi di estensione e LINQ  
 Poiché il tipo <xref:System.String> implementa <xref:System.Collections.Generic.IEnumerable%601> è possibile usare i metodi di estensione definiti nella classe <xref:System.Linq.Enumerable> sulle stringhe. Per evitare confusioni a livello visivo questi metodi sono esclusi da IntelliSense per il tipo <xref:System.String>, ma sono comunque disponibili. È anche possibile usare espressioni di query LINQ sulle stringhe. Per altre informazioni, vedere [LINQ e stringhe](../concepts/linq/linq-and-strings.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|[Come modificare il contenuto delle stringhe](../../how-to/modify-string-contents.md)|Illustra le tecniche per trasformare le stringhe e modificare il contenuto di queste.|  
|[Come confrontare le stringhe](../../how-to/compare-strings.md)|Illustra come eseguire confronti di stringhe tra ordinali e impostazioni cultura.|  
|[Come concatenare più stringhe](../../how-to/concatenate-multiple-strings.md)|Illustra vari modi per unire più stringhe in una.|
|[Come analizzare le stringhe con String. Split](../../how-to/parse-strings-using-split.md)|Esempi di codice che illustrano come usare il metodo `String.Split` per analizzare le stringhe.|  
|[Come cercare stringhe](../../how-to/search-strings.md)|Spiega come eseguire la ricerca di testo specifico o di motivi nelle stringhe.|  
|[Come determinare se una stringa rappresenta un valore numerico](./how-to-determine-whether-a-string-represents-a-numeric-value.md)|Viene illustrato come analizzare in modo sicuro una stringa per verificare se ha un valore numerico valido.|  
|[Interpolazione di stringhe](../../language-reference/tokens/interpolated.md)|Descrive la funzionalità di interpolazione di stringhe che offre una sintassi efficiente per formattare le stringhe.|
|[Operazioni di base sulle stringhe](../../../standard/base-types/basic-string-operations.md)|Fornisce collegamenti ad argomenti che usano metodi <xref:System.String?displayProperty=nameWithType> e <xref:System.Text.StringBuilder?displayProperty=nameWithType> per eseguire operazioni di base sulle stringhe.|  
|[Analisi di stringhe](../../../standard/base-types/parsing-strings.md)|Descrive come convertire le rappresentazioni stringa dei tipi di base .NET in istanze dei tipi corrispondenti.|  
|[Analisi di stringhe di data e ora in .NET](../../../standard/base-types/parsing-datetime.md)|Illustra come convertire una stringa come "24/01/2008" in un oggetto <xref:System.DateTime?displayProperty=nameWithType>.|  
|[Confronto di stringhe](../../../standard/base-types/comparing.md)|Informazioni su come confrontare le stringhe ed esempi in C# e Visual Basic.|  
|[Uso della classe StringBuilder](../../../standard/base-types/stringbuilder.md)|Descrive come creare e modificare oggetti stringa dinamici tramite la classe <xref:System.Text.StringBuilder>.|  
|[LINQ e stringhe](../concepts/linq/linq-and-strings.md)|Informazioni su come eseguire varie operazioni sulle stringhe tramite query LINQ.|  
|[Guida per programmatori C#](../index.md)|Collegamenti ad argomenti che spiegano i costrutti di programmazione in C#.|  
