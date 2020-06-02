---
title: Opzioni di espressioni regolari
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, options
- constructs, options
- .NET Framework regular expressions, options
- inline option constructs
- options parameter
ms.assetid: c82dc689-7e82-4767-a18d-cd24ce5f05e9
ms.openlocfilehash: 8c742c855234bfd9653bb57036c41e7ccce66295
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289291"
---
# <a name="regular-expression-options"></a>Opzioni di espressioni regolari

Per impostazione predefinita, il confronto di una stringa di input con qualsiasi carattere letterale in un criterio di ricerca di espressioni regolari prevede la distinzione tra maiuscole e minuscole. Gli spazi vuoti in un criterio di ricerca di espressioni regolari vengono interpretati come caratteri di spazio vuoto letterali e i gruppi di acquisizione in un'espressione regolare sono denominati in modo sia implicito che esplicito. È possibile modificare questi e molti altri aspetti del comportamento predefinito delle espressioni regolari specificando le relative opzioni. Queste opzioni, elencate nella tabella seguente, possono essere incluse inline come parte del criterio di ricerca di espressioni regolari o in alternativa fornite a un costruttore della classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> o a un metodo statico dei criteri di ricerca come valore di enumerazione <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.

|Membro RegexOptions|Carattere inline|Effetto|
|-------------------------|----------------------|------------|
|<xref:System.Text.RegularExpressions.RegexOptions.None>|Non disponibile|Usare il comportamento predefinito. Per altre informazioni, vedere [Opzioni predefinite](#default-options).|
|<xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase>|`i`|Usa la corrispondenza che non fa distinzione tra maiuscole e minuscole. Per altre informazioni, vedere [Corrispondenza senza distinzione tra maiuscole e minuscole](#case-insensitive-matching).|
|<xref:System.Text.RegularExpressions.RegexOptions.Multiline>|`m`|Usare la modalità multiriga, in cui `^` e `$` corrispondono all'inizio e alla fine di una riga, anziché all'inizio e alla fine della stringa di input. Per altre informazioni, vedere [Modalità multiriga](#multiline-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.Singleline>|`s`|Usa la modalità a riga singola, in cui il punto (.) corrisponde a qualsiasi carattere anziché a tutti i caratteri tranne `\n`. Per altre informazioni, vedere [modalità a riga singola](#single-line-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture>|`n`|Non acquisire gruppi senza nome. Le uniche acquisizioni valide sono i gruppi denominati o numerati in modo esplicito in formato `(?<`*nome*`>` *sottoespressione*`)`. Per altre informazioni, vedere [Solo acquisizioni esplicite](#explicit-captures-only).|
|<xref:System.Text.RegularExpressions.RegexOptions.Compiled>|Non disponibile|Compila l'espressione regolare in un assembly. Per altre informazioni, vedere [Espressioni regolari compilate](#compiled-regular-expressions).|
|<xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace>|`x`|Esclude gli spazi vuoti senza caratteri di escape nel criterio e abilita i commenti dopo un simbolo di cancelletto (`#`). Per altre informazioni, vedere [Ignora spazi vuoti](#ignore-white-space).|
|<xref:System.Text.RegularExpressions.RegexOptions.RightToLeft>|Non disponibile|Modifica la direzione di ricerca. La ricerca viene eseguita da destra verso sinistra, anziché da sinistra verso destra. Per altre informazioni, vedere [Modalità da destra a sinistra](#right-to-left-mode).|
|<xref:System.Text.RegularExpressions.RegexOptions.ECMAScript>|Non disponibile|Abilita un comportamento conforme a ECMAScript per l'espressione. Per altre informazioni, vedere [Comportamento di corrispondenza ECMAScript](#ecmascript-matching-behavior).|
|<xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant>|Non disponibile|Ignora le differenze di cultura nella lingua. Per altre informazioni, vedere [Confronto usando la lingua inglese](#comparison-using-the-invariant-culture).|

## <a name="specifying-the-options"></a>Specifica delle opzioni

È possibile specificare le opzioni per le espressioni regolari in tre modi:

- Nel parametro `options` di un costruttore della classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> o di un metodo statico (`Shared` in Visual Basic) dei criteri di ricerca, ad esempio <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%29> o <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>. Il parametro `options` è una combinazione OR bit per bit dei valori enumerati <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.

  Quando vengono specificate le opzioni per un'istanza di <xref:System.Text.RegularExpressions.Regex> usando il parametro `options` di un costruttore di classe, le opzioni vengono assegnate alla proprietà <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>. Tuttavia, la proprietà <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType> non rispecchia le opzioni inline nel criterio di ricerca di espressioni regolari stesso.

  Di seguito ne viene illustrato un esempio. Il parametro `options` del metodo <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> viene usato per abilitare la corrispondenza senza distinzione tra maiuscole e minuscole e per ignorare gli spazi vuoti nel criterio durante l'identificazione delle parole che iniziano con la lettera "d".

  [!code-csharp[Conceptual.Regex.Language.Options#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#6)]
  [!code-vb[Conceptual.Regex.Language.Options#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#6)]

- Applicando le opzioni inline in un criterio di ricerca di espressioni regolari con la sintassi `(?imnsx-imnsx)`. L'opzione si applica al criterio dal punto in cui viene definita fino alla fine del criterio oppure fino al punto in cui viene annullata da un'altra opzione inline. Si noti che la proprietà <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType> di un'istanza di <xref:System.Text.RegularExpressions.Regex> non rispecchia queste opzioni inline. Per altre informazioni, vedere l'argomento [Costrutti vari](miscellaneous-constructs-in-regular-expressions.md).

  Di seguito ne viene illustrato un esempio. Le opzioni online vengono usate per abilitare la corrispondenza senza distinzione tra maiuscole e minuscole e per ignorare gli spazi vuoti nel criterio durante l'identificazione delle parole che iniziano con la lettera "d".

  [!code-csharp[Conceptual.Regex.Language.Options#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#7)]
  [!code-vb[Conceptual.Regex.Language.Options#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#7)]

- Applicando opzioni inline in un particolare costrutto di raggruppamento in un criterio di ricerca di espressioni regolari con la sintassi `(?imnsx-imnsx:` *sottoespressione* `)` . Nessun segno prima di un set di opzioni attiva il set. Un segno meno prima di un set di opzioni disattiva il set. ( `?` è una parte fissa della sintassi del costrutto di linguaggio richiesta se le opzioni sono abilitate o disabilitate). L'opzione si applica solo a tale gruppo. Per altre informazioni, vedere [Costrutti di raggruppamento](grouping-constructs-in-regular-expressions.md).

  Di seguito ne viene illustrato un esempio. Le opzioni online vengono usate in un costrutto di raggruppamento per abilitare la corrispondenza senza distinzione tra maiuscole e minuscole e per ignorare gli spazi vuoti nel criterio durante l'identificazione delle parole che iniziano con la lettera "d".

  [!code-csharp[Conceptual.Regex.Language.Options#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#8)]
  [!code-vb[Conceptual.Regex.Language.Options#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#8)]

Se le opzioni vengono specificate inline, un segno meno (`-`) prima di un'opzione o di un set di opzioni consente di disattivare tali opzioni. Ad esempio, il costrutto inline `(?ix-ms)` attiva le opzioni <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> e <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> e disattiva le opzioni <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> e <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>. Per impostazione predefinita, tutte le opzioni di espressioni regolari sono disattivate.

> [!NOTE]
> In caso di conflitto tra le opzioni di espressione regolare specificate nel parametro `options` di un costruttore o di una chiamata a metodo e le opzioni specificate inline in un criterio di ricerca di espressioni regolari, vengono usate le opzioni inline.

Le cinque opzioni di espressione regolare seguenti possono essere impostate sia con il parametro options che inline:

- <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>

Le cinque opzioni di espressione regolare seguenti possono essere impostate usando il parametro `options`, ma non inline:

- <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType>

- <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType>

## <a name="determining-the-options"></a>Determinazione delle opzioni

È possibile determinare le opzioni fornite a un oggetto <xref:System.Text.RegularExpressions.Regex> al momento della creazione dell'istanza recuperando il valore della proprietà <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> di sola lettura. Questa proprietà è particolarmente utile per determinare le opzioni definite per un'espressione regolare compilata creata dal metodo <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>.

Per testare la presenza di qualsiasi opzione eccetto <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, eseguire un'operazione AND con il valore della proprietà <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> e il valore <xref:System.Text.RegularExpressions.RegexOptions> desiderato. Testare quindi se il risultato corrisponde al valore <xref:System.Text.RegularExpressions.RegexOptions>. L'esempio seguente testa se l'opzione <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> è stata impostata.

[!code-csharp[Conceptual.Regex.Language.Options#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#19)]
[!code-vb[Conceptual.Regex.Language.Options#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#19)]

Per testare <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, determinare se il valore della proprietà <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=nameWithType> sia uguale a <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>, come illustrato nell'esempio seguente.

[!code-csharp[Conceptual.Regex.Language.Options#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#20)]
[!code-vb[Conceptual.Regex.Language.Options#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#20)]

Nelle sezioni seguenti sono riportate le opzioni supportate dalle espressioni regolari in .NET.

## <a name="default-options"></a>Opzioni predefinite

L'opzione <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType> indica che non sono state specificate opzioni e che il motore delle espressioni regolari usa il comportamento predefinito. Sono inclusi gli elementi seguenti:

- Il criterio viene interpretato come canonico anziché come espressione regolare ECMAScript.

- Il criterio di ricerca di espressioni regolari viene messo in corrispondenza nella stringa di input da sinistra verso destra.

- Nei confronti viene fatta distinzione tra maiuscole e minuscole.

- Gli elementi di linguaggio `^` e `$` corrispondono all'inizio e alla fine della stringa di input.

- L'elemento di linguaggio `.` corrisponde a qualsiasi carattere tranne `\n`.

- Qualsiasi spazio vuoto in un criterio di ricerca di espressioni regolari viene interpretato come spazio letterale.

- Nel confronto del criterio con la stringa di input vengono usate le convenzioni delle impostazioni cultura correnti.

- I gruppi di acquisizione nel criterio di ricerca di espressioni regolari sono sia impliciti che espliciti.

> [!NOTE]
> L'opzione <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType> non ha un equivalente inline. Quando le opzioni di espressioni regolari vengono applicate inline, il comportamento predefinito viene ripristinato opzione per opzione, disattivando una particolare opzione. Ad esempio, `(?i)` disattiva il confronto senza distinzione tra maiuscole e minuscole e `(?-i)` lo ripristina.

Poiché l'opzione <xref:System.Text.RegularExpressions.RegexOptions.None?displayProperty=nameWithType>rappresenta il comportamento predefinito del motore delle espressioni regolari, raramente viene specificata in modo esplicito in una chiamata a metodo. Viene invece chiamato un costruttore o un metodo statico dei criteri di ricerca senza un parametro `options`.

## <a name="case-insensitive-matching"></a>Corrispondenza senza distinzione tra maiuscole e minuscole

L'opzione <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase>, o l'opzione inline `i`, fornisce la corrispondenza senza distinzione tra maiuscole e minuscole. Per impostazione predefinita, vengono usate le convenzioni sulla combinazione di maiuscole e minuscole delle impostazioni cultura correnti.

L'esempio seguente definisce un criterio di ricerca di espressioni regolari, `\bthe\w*\b`, che trova la corrispondenza di tutte le parole che iniziano con "the". Poiché la prima chiamata al metodo <xref:System.Text.RegularExpressions.Regex.Match%2A> usa il confronto predefinito con distinzione tra maiuscole e minuscole, l'output indica che la stringa "The" che inizia la frase non viene individuata come corrispondenza. La corrispondenza viene individuata quando il metodo <xref:System.Text.RegularExpressions.Regex.Match%2A> viene chiamato con le opzioni impostate su <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase>.

[!code-csharp[Conceptual.Regex.Language.Options#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case1.cs#1)]
[!code-vb[Conceptual.Regex.Language.Options#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case1.vb#1)]

L'esempio seguente modifica il criterio di ricerca di espressioni regolari dell'esempio precedente in modo da usare opzioni inline anziché il parametro `options` per fornire il confronto senza distinzione fra maiuscole e minuscole. Il primo criterio definisce l'opzione che non prevede la distinzione tra maiuscole e minuscole in un costrutto di raggruppamento che si applica solo alla lettera "t" nella stringa "the". Poiché il costrutto di opzione si trova all'inizio del criterio, il secondo criterio applica l'opzione che non prevede la distinzione tra maiuscole e minuscole all'intera espressione regolare.

[!code-csharp[Conceptual.Regex.Language.Options#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case2.cs#2)]
[!code-vb[Conceptual.Regex.Language.Options#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case2.vb#2)]

## <a name="multiline-mode"></a>Modalità multiriga

L'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>, o l'opzione inline `m`, consente al motore delle espressioni regolari di gestire una stringa di input composta da più righe. Modifica l'interpretazione degli elementi di linguaggio `^` e `$` in modo che corrispondano all'inizio e alla fine di una riga invece che all'inizio e alla fine della stringa di input.

Per impostazione predefinita, `$` trova la corrispondenza solo alla fine della stringa di input. Se si specifica l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>, viene trovata la corrispondenza di un carattere di nuova riga (`\n`) o della fine della stringa di input. Non viene tuttavia trovata la corrispondenza di una combinazione carattere di ritorno a capo/avanzamento riga. A questo scopo, usare la sottoespressione `\r?$` anziché semplicemente `$`.

L'esempio seguente estrae i nomi e i punteggi dei giocatori di bowling e li aggiunge a una raccolta <xref:System.Collections.Generic.SortedList%602> che li ordina in ordine decrescente. Il metodo <xref:System.Text.RegularExpressions.Regex.Matches%2A> viene chiamato due volte. Nella prima chiamata al metodo, l'espressione regolare è `^(\w+)\s(\d+)$` e non sono impostate opzioni. Come mostra l'output, poiché il motore delle espressioni regolari non trova corrispondenza tra il criterio di input e l'inizio e la fine della stringa di input, non vengono individuate corrispondenze. Nella seconda chiamata al metodo, l'espressione regolare viene modificata in `^(\w+)\s(\d+)\r?$` e le opzioni sono impostate su <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>. Come mostra l'output, la corrispondenza tra i nomi e i punteggi viene individuata correttamente e i punteggi vengono visualizzati in ordine decrescente.

[!code-csharp[Conceptual.Regex.Language.Options#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/multiline1.cs#3)]
[!code-vb[Conceptual.Regex.Language.Options#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/multiline1.vb#3)]

Il criterio di ricerca di espressioni regolari `^(\w+)\s(\d+)\r*$` è definito nel modo illustrato nella tabella seguente.

|Modello|Descrizione|
|-------------|-----------------|
|`^`|Comincia all'inizio della riga.|
|`(\w+)`|Trova la corrispondenza di uno o più caratteri alfanumerici. Equivale al primo gruppo di acquisizione.|
|`\s`|Trova la corrispondenza con uno spazio vuoto.|
|`(\d+)`|Trova la corrispondenza con una o più cifre decimali. Equivale al secondo gruppo di acquisizione.|
|`\r?`|Trova la corrispondenza di zero o un carattere di ritorno a capo.|
|`$`|Termina alla fine della riga.|

L'esempio di seguito equivale al precedente, tranne il fatto che viene usata l'opzione inline `(?m)` per impostare l'opzione multiriga.

[!code-csharp[Conceptual.Regex.Language.Options#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/multiline2.cs#4)]
[!code-vb[Conceptual.Regex.Language.Options#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/multiline2.vb#4)]

## <a name="single-line-mode"></a>Modalità a riga singola.

L'opzione <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>, o l'opzione inline `s`, consente al motore delle espressioni regolari di gestire la stringa di input come se fosse composta da una sola riga. Lo fa modificando il comportamento dell'elemento di linguaggio punto (`.`) in modo che corrisponda a qualsiasi carattere anziché a qualsiasi carattere ad eccezione del carattere di nuova riga `\n` o \u000A.

L'esempio seguente illustra come cambia il comportamento dell'elemento di linguaggio `.` quando si usa l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>. L'espressione regolare `^.+` parte dall'inizio della stringa e individua una corrispondenza per ogni carattere. Per impostazione predefinita, la corrispondenza termina alla fine della prima riga. Il criterio di ricerca di espressioni regolari trova la corrispondenza del carattere di ritorno a capo, `\r` o \u000D, ma non di `\n`. Poiché l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> interpreta l'intera stringa di input come riga singola, ottiene una corrispondenza per ogni carattere nella stringa di input, incluso `\n`.

[!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
[!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]

L'esempio di seguito equivale al precedente, tranne il fatto che viene usata l'opzione inline `(?s)` per impostare la modalità a riga singola.

[!code-csharp[Conceptual.Regex.Language.Options#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/singleline1.cs#5)]
[!code-vb[Conceptual.Regex.Language.Options#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/singleline1.vb#5)]

## <a name="explicit-captures-only"></a>Solo acquisizioni esplicite

Per impostazione predefinita, i gruppi di acquisizione vengono definiti dall'uso di parentesi nel criterio di ricerca di espressioni regolari. Ai gruppi denominati viene assegnato un nome o un numero dall' `(?<` opzione di linguaggio *nome* `>` *sottoespressione* `)` , mentre i gruppi non denominati sono accessibili in base all'indice. Nell'oggetto <xref:System.Text.RegularExpressions.GroupCollection> i gruppi non denominati precedono i gruppi denominati.

I costrutti di raggruppamento vengono spesso usati solo per applicare quantificatori a più elementi di linguaggio e le sottostringhe acquisite non sono di alcun interesse. Ad esempio, se l'espressione regolare seguente:

`\b\(?((\w+),?\s?)+[\.!?]\)?`

è intesa solo per l'estrazione di frasi che terminano con un punto, un punto esclamativo o un punto interrogativo da un documento, solo la frase risultante (rappresentata dall'oggetto <xref:System.Text.RegularExpressions.Match>) rappresenta un elemento di interesse. Le singola parole nella raccolta non lo sono.

I gruppi di acquisizione che successivamente non vengono usati possono risultare costosi, in quanto il motore delle espressioni regolari deve popolare entrambi gli oggetti raccolta <xref:System.Text.RegularExpressions.GroupCollection> e <xref:System.Text.RegularExpressions.CaptureCollection>. In alternativa, si può usare l'opzione <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType> o l'opzione inline `n` per specificare che le sole acquisizioni valide sono i gruppi denominati o numerati in modo esplicito definiti dal costrutto `(?<`*nome*`>` *sottoespressione*`)`.

L'esempio seguente mostra informazioni sulle corrispondenze restituite dal criterio di ricerca di espressioni regolari `\b\(?((\w+),?\s?)+[\.!?]\)?` quando viene chiamato il metodo <xref:System.Text.RegularExpressions.Regex.Match%2A> con e senza l'opzione <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>. Come mostra l'output della prima chiamata al metodo, il motore delle espressioni regolari popola interamente gli oggetti raccolta <xref:System.Text.RegularExpressions.GroupCollection> e <xref:System.Text.RegularExpressions.CaptureCollection> con informazioni sulle sottostringhe acquisite. Poiché il secondo metodo viene chiamato con `options` impostato su <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>, non acquisisce informazioni sui gruppi.

[!code-csharp[Conceptual.Regex.Language.Options#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit1.cs#9)]
[!code-vb[Conceptual.Regex.Language.Options#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit1.vb#9)]

Il criterio di ricerca di espressioni regolari `\b\(?((?>\w+),?\s?)+[\.!?]\)?` è definito nel modo illustrato nella tabella seguente.

|Modello|Descrizione|
|-------------|-----------------|
|`\b`|Inizia dal confine di una parola.|
|`\(?`|Trova la corrispondenza di una o nessuna parentesi di apertura ("(").|
|`(?>\w+),?`|Trova la corrispondenza di uno o più caratteri alfanumerici seguiti da una o nessuna virgola. Non eseguire il backtracking quando viene trovata la corrispondenza di caratteri alfanumerici.|
|`\s?`|Trova la corrispondenza di uno o nessuno spazio vuoto.|
|`((\w+),?\s?)+`|Trova una o più volte la corrispondenza di una combinazione di uno o più caratteri alfanumerici, una o nessuna virgola e uno o nessuno spazio vuoto.|
|`[\.!?]\)?`|Trova la corrispondenza di qualsiasi dei tre simboli di punteggiatura, seguiti da una o nessuna parentesi di chiusura (")").|

È anche possibile usare l'elemento inline `(?n)` per disattivare le acquisizioni automatiche. L'esempio seguente modifica il criterio di ricerca di espressioni regolari precedente in modo da usare l'elemento inline `(?n)` anziché l'opzione <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Regex.Language.Options#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit2.cs#10)]
[!code-vb[Conceptual.Regex.Language.Options#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit2.vb#10)]

Infine, si può usare l'elemento di gruppo inline `(?n:)` per disattivare le acquisizioni automatiche gruppo per gruppo. L'esempio di seguito modifica il criterio precedente per disattivare le acquisizioni non denominate nel gruppo esterno, `((?>\w+),?\s?)`. Notare che in questo modo vengono disattivare le acquisizioni non denominate anche nel gruppo interno.

[!code-csharp[Conceptual.Regex.Language.Options#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit3.cs#11)]
[!code-vb[Conceptual.Regex.Language.Options#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit3.vb#11)]

## <a name="compiled-regular-expressions"></a>Espressioni regolari compilate

Per impostazione predefinita, le espressioni regolari in .NET vengono interpretate. Quando viene creata un'istanza di un oggetto <xref:System.Text.RegularExpressions.Regex> o viene chiamato un metodo <xref:System.Text.RegularExpressions.Regex> statico, il criterio di ricerca di espressioni regolari viene convertito in un set di codici operativi personalizzati, che vengono usati da un interprete per eseguire l'espressione regolare. Questo comporta un compromesso: il tempo di inizializzazione del motore delle espressioni regolari viene ridotto al minimo, a scapito delle prestazioni in fase di esecuzione.

È possibile usare espressioni regolari compilate anziché interpretate mediante l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>. In questo caso, quando un criterio viene passato al motore delle espressioni regolari, viene convertito in un set di codici operativi e quindi in MSIL, che può essere passato direttamente a Common Language Runtime. Le espressioni regolari compilate massimizzano le prestazioni in fase di esecuzione a scapito del tempo di inizializzazione.

> [!NOTE]
> Un'espressione regolare può essere compilata solo fornendo il valore <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> al parametro `options` di un costruttore di classe <xref:System.Text.RegularExpressions.Regex> o di un metodo statico dei criteri di ricerca. Non è disponibile come opzione inline.

È possibile usare le espressioni regolari compilate sia nelle chiamate a occorrenze statiche che nelle chiamate a istanze di espressioni regolari. Nelle espressioni regolari statiche, l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> viene passata al parametro `options` del metodo dei criteri di ricerca di espressioni regolari. Nelle istanze di espressioni regolari, viene passato al parametro `options` del costruttore della classe <xref:System.Text.RegularExpressions.Regex>. In entrambi i casi, le prestazioni risultano migliorate.

Il miglioramento delle prestazioni, tuttavia, si verifica solo in presenza delle condizioni seguenti:

- Un oggetto <xref:System.Text.RegularExpressions.Regex> che rappresenta una particolare espressione regolare viene usato in più chiamate a metodi dei criteri di ricerca di espressioni regolari.

- L'oggetto <xref:System.Text.RegularExpressions.Regex> non può uscire dall'ambito, dunque può essere riutilizzato.

- Un'espressione regolare statica viene usata in più chiamate a metodi dei criteri di ricerca di espressioni regolari. (Il miglioramento delle prestazioni è possibile perché le espressioni regolari usate nelle chiamate al metodo statico vengono memorizzate nella cache dal motore delle espressioni regolari.)

> [!NOTE]
> L'opzione <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> non è correlata al metodo <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>, che crea un assembly speciale che contiene espressioni regolari compilate predefinite.

## <a name="ignore-white-space"></a>Ignora spazi vuoti

Per impostazione predefinita, gli spazi vuoti in un criterio di ricerca di espressioni regolari sono significativi. Forzano il motore delle espressioni regolari a trovare una corrispondenza del carattere spazio nella stringa di input. Per questo motivo, l'espressione regolare "`\b\w+\s`" e "`\b\w+` " sono espressioni regolari pressoché equivalenti. Inoltre, quando il simbolo di cancelletto (#) viene incontrato in un criterio di ricerca di espressioni regolari, viene interpretato come carattere letterale di cui trovare la corrispondenza.

L'opzione <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>, o l'opzione inline `x`, modifica questo comportamento predefinito come segue:

- Gli spazi vuoti non di escape nel criterio di ricerca di espressioni regolari vengono ignorati. Per far parte di un criterio di ricerca di espressioni regolari, gli spazi vuoti devono essere preceduti da un carattere di escape (ad esempio `\s` o "`\` ").

- Il simbolo di cancelletto (#) viene interpretato come l'inizio di un commento anziché come un carattere letterale. Tutto il testo nel criterio di ricerca di espressioni regolari, dal carattere # alla fine della stringa, viene interpretato come un commento.

Nei casi seguenti, tuttavia, gli spazi in un'espressione regolare non vengono ignorati anche se si usa l'opzione <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>:

- Uno spazio vuoto in una classe di caratteri viene sempre interpretato letteralmente. Ad esempio, il criterio di ricerca di espressioni regolari `[ .,;:]` trova la corrispondenza di qualsiasi spazio vuoto, punto, virgola, punto e virgola o due punti.

- Gli spazi vuoti non sono consentiti all'interno di un quantificatore racchiuso tra parentesi, ad esempio `{` *n* `}` , `{` *n* `,}` e `{` *n* `,` *m* `}` . Ad esempio, il criterio di ricerca di espressioni regolari `\d{1, 3}` non riesce a trovare sequenze di cifre da una a tre cifre perché contiene uno spazio vuoto.

- Gli spazi vuoti non sono consentiti all'interno di una sequenza di caratteri che introduce un elemento di linguaggio. Ad esempio:

  - L'elemento del linguaggio `(?:` *sottoespressione* `)` rappresenta un gruppo di non acquisizione e la `(?:` parte dell'elemento non può contenere spazi incorporati. Il criterio `(? :` *sottoespressione* `)` genera un'eccezione <xref:System.ArgumentException> in fase di esecuzione perché il motore delle espressioni regolari non può analizzare il criterio e il criterio `( ?:` *sottoespressione* `)` non riesce a trovare la corrispondenza di *sottoespressione*.

  - Il nome dell'elemento `\p{` *name* `}` di linguaggio, che rappresenta una categoria Unicode o un blocco denominato, non può includere spazi incorporati nella `\p{` parte dell'elemento. Se si include uno spazio vuoto, l'elemento genera un'eccezione <xref:System.ArgumentException> in fase di esecuzione.

Abilitare questa opzione consente di semplificare espressioni regolari spesso difficili da analizzare e capire. Migliora la leggibilità e rende possibile documentare un'espressione regolare.

L'esempio di seguito definisce il criterio di ricerca di espressioni regolari seguente:

`\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence.`

Questo criterio è simile a quello definito nella sezione [Solo acquisizioni esplicite](#explicit-captures-only), ad eccezione del fatto che usa l'opzione <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> per ignorare lo spazio vuoto del criterio.

[!code-csharp[Conceptual.Regex.Language.Options#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace1.cs#12)]
[!code-vb[Conceptual.Regex.Language.Options#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace1.vb#12)]

L'esempio seguente usa l'opzione inline `(?x)` per ignorare lo spazio vuoto del criterio.

[!code-csharp[Conceptual.Regex.Language.Options#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace2.cs#13)]
[!code-vb[Conceptual.Regex.Language.Options#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace2.vb#13)]

## <a name="right-to-left-mode"></a>Modalità da destra a sinistra

Per impostazione predefinita, il motore delle espressioni regolari effettua la ricerca da sinistra a destra. È possibile invertire la direzione della ricerca tramite l'opzione <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType>. La ricerca inizia automaticamente nella posizione dell'ultimo carattere della stringa. Per i metodi dei criteri di ricerca che includono un parametro della posizione iniziale, ad esempio <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.Int32%29?displayProperty=nameWithType>, la posizione iniziale è l'indice della posizione dell'ultimo carattere a destra in corrispondenze del quale ha inizio la ricerca.

> [!NOTE]
> La modalità da destra a sinistra è disponibile solo fornendo il valore <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType> al parametro `options` di un costruttore della classe <xref:System.Text.RegularExpressions.Regex> o un metodo statico dei criteri di ricerca. Non è disponibile come opzione inline.

L'opzione <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType> modifica solo la direzione di ricerca; non interpreta il criterio di ricerca di espressioni regolari da destra a sinistra. Ad esempio, l'espressione regolare `\bb\w+\s` trova le corrispondenze di parole che iniziano con la lettera "b" e sono seguite da uno spazio vuoto. Nell'esempio seguente, la stringa di input è costituita da tre parole che comprendono uno o più caratteri "b". La prima parola inizia con "b", la seconda termina con "b" e la terza contiene due caratteri "b" al centro. Come mostra l'output dell'esempio, solo le prime parole corrispondono al criterio di ricerca di espressioni regolari.

[!code-csharp[Conceptual.Regex.Language.Options#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft1.cs#17)]
[!code-vb[Conceptual.Regex.Language.Options#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft1.vb#17)]

Si noti inoltre che l'asserzione lookahead (l' `(?=` elemento di linguaggio *sottoespressione* `)` ) e l'asserzione lookbehind (l' `(?<=` elemento di linguaggio *sottoespressione* `)` ) non cambiano direzione. Le asserzioni lookahead cercano a destra, mentre le asserzioni lookbehind cercano a sinistra. Ad esempio, l'espressione regolare `(?<=\d{1,2}\s)\w+,?\s\d{4}` usa l'asserzione lookbehind per testare una data che precede il nome di un mese. L'espressione regolare trova quindi la corrispondenza di mese e anno. Per informazioni sulle asserzioni lookahead e lookbehind, vedere [Costrutti di raggruppamento](grouping-constructs-in-regular-expressions.md).

[!code-csharp[Conceptual.Regex.Language.Options#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft2.cs#18)]
[!code-vb[Conceptual.Regex.Language.Options#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft2.vb#18)]

Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.

|Modello|Descrizione|
|-------------|-----------------|
|`(?<=\d{1,2}\s)`|L'inizio della corrispondenza deve essere preceduto da una o due cifre decimali seguite da uno spazio.|
|`\w+`|Trova la corrispondenza di uno o più caratteri alfanumerici.|
|`,?`|Trova la corrispondenza di una o nessuna virgola.|
|`\s`|Trova la corrispondenza con uno spazio vuoto.|
|`\d{4}`|Trova la corrispondenza con quattro cifre decimali.|

## <a name="ecmascript-matching-behavior"></a>Comportamento di corrispondenza ECMAScript

Per impostazione predefinita, il motore delle espressioni regolari usa un comportamento canonico nella ricerca di corrispondenza di un criterio di ricerca di espressioni regolari nel testo di input. Si può però istruire il motore delle espressioni regolari in modo che usi il comportamento di corrispondenza ECMAScript specificando l'opzione <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType>.

> [!NOTE]
> Il comportamento conforme a ECMAScript è disponibile solo fornendo il valore <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType> al parametro `options` di un costruttore della classe <xref:System.Text.RegularExpressions.Regex> o un metodo statico dei criteri di ricerca. Non è disponibile come opzione inline.

L'opzione <xref:System.Text.RegularExpressions.RegexOptions.ECMAScript?displayProperty=nameWithType> può essere combinata solo con le opzioni <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> e <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>. L'uso di qualsiasi altra opzione in un'espressione regolare genera un'eccezione <xref:System.ArgumentOutOfRangeException>.

Il comportamento di ECMAScript e quello delle espressioni regolari canoniche differiscono in tre aspetti: sintassi delle classi di caratteri, gruppi di acquisizione autoreferenziali e interpretazione degli ottali rispetto a quella dei backreference.

- Sintassi delle classi di caratteri. Poiché le espressioni regolari canoniche supportano Unicode a differenza di ECMAScript, le classi di caratteri in ECMAScript hanno una sintassi più limitata e alcuni elementi di linguaggio delle classi di caratteri hanno un significato diverso. Ad esempio, ECMAScript non supporta elementi di linguaggio come la categoria Unicode o gli elementi di blocco `\p` e `\P`. Analogamente, l'elemento `\w`, che trova la corrispondenza di un carattere alfanumerico è equivalente alla classe di caratteri `[a-zA-Z_0-9]` quando si usa ECMAScript e a `[\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]` quando si usa il comportamento canonico. Per altre informazioni, vedere [classi di caratteri](character-classes-in-regular-expressions.md).

  L'esempio seguente illustra le differenze tra i criteri di ricerca canonici ed ECMAScript. Definisce un'espressione regolare, `\b(\w+\s*)+`, che trova la corrispondenza di parole seguite da spazi vuoti. L'input è costituito da due stringhe, una che usa il set di caratteri latini e l'altra che usa il set di caratteri cirillici. Come mostra l'output, la chiamata al metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> che usa i criteri di ricerca ECMAScript non riesce a trovare la corrispondenza delle parole in cirillico, mentre la chiamata al metodo che usa i criteri di ricerca individua trova la corrispondenza.

  [!code-csharp[Conceptual.Regex.Language.Options#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript1.cs#16)]
  [!code-vb[Conceptual.Regex.Language.Options#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript1.vb#16)]

- Gruppi di acquisizione autoreferenziali. È necessario aggiornare una classe di acquisizione di espressioni regolari con un backreference autoreferenziale ogni volta che viene eseguita un'iterazione dell'acquisizione. Come mostra l'esempio seguente, questa funzionalità consente all'espressione regolare `((a+)(\1) ?)+` di trovare la corrispondenza della stringa di input " aa aaaa aaaaaa " quando si usa ECMAScript, ma non quando si usano i criteri di ricerca canonici.

  [!code-csharp[Conceptual.Regex.Language.Options#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript2.cs#21)]
  [!code-vb[Conceptual.Regex.Language.Options#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript2.vb#21)]

  L'espressione regolare è definita nel modo illustrato nella tabella seguente.

  |Modello|Descrizione|
  |-------------|-----------------|
  |(a+)|Trova la corrispondenza della lettera "a" una o più volte. Equivale al secondo gruppo di acquisizione.|
  |(\1)|Trova la corrispondenza della sottostringa acquisita dal primo gruppo di acquisizione. Equivale al terzo gruppo di acquisizione.|
  |?|Trova la corrispondenza di uno o nessuno spazio.|
  |((a+)(\1) ?)+|Trova una o più volte la corrispondenza di uno o più caratteri "a" seguiti da una stringa che corrisponde al primo gruppo di acquisizione seguito da zero o da uno spazio vuoto. Equivale al primo gruppo di acquisizione.|

- Risoluzione delle ambiguità tra caratteri di escape ottali e backreference. La tabella seguente contiene un riepilogo delle differenze tra l'interpretazione ottale e quella dei backreference nelle espressioni regolari canoniche e di ECMAScript.

  |Espressione regolare‏|Comportamento canonico|Comportamento ECMAScript|
  |------------------------|------------------------|-------------------------|
  |`\0` seguito da cifre ottali comprese tra 0 e 2|Interpretare come un ottale. Ad esempio, `\044` viene sempre interpretato come un valore ottale e significa "$".|Stesso comportamento.|
  |`\` seguito da una cifra compresa tra 1 e 9, quindi da nessuna cifra decimale aggiuntiva|Interpretare come un backreference. Ad esempio, `\9` rappresenta sempre un backreference 9, anche se il nono gruppo di acquisizione non esiste. Se il gruppo di acquisizione non esiste, il parser dell'espressione regolare genera un'eccezione <xref:System.ArgumentException>.|Se esiste un gruppo di acquisizione di una singola cifra decimale, il carattere viene considerato un backreference di tale cifra. Altrimenti il valore viene interpretato come un valore letterale.|
  |`\` seguito da una cifra compresa tra 1 e 9, quindi da ulteriori cifre decimali|Interpretare le cifre come un valore decimale. Se tale gruppo di acquisizione esiste, l'espressione viene interpretata come un backreference.<br /><br /> In caso contrario, interpretare le cifre ottali iniziali fino all'ottale 377, ovvero considerare solo gli 8 bit inferiori del valore. Interpretare le cifre restanti come valori letterali. Ad esempio, nell'espressione `\3000`, se il gruppo di acquisizione 300 esiste, l'espressione viene interpretata come un backreference 300; se il gruppo di acquisizione 300 non esiste, viene interpretata come ottale 300 seguito da 0.|Interpretare come un backreference convertendo il maggior numero possibile di cifre a un valore decimale che si può riferire a un'acquisizione. Se non è possibile convertire alcuna cifra, interpretare il carattere come un ottale usando le cifre ottali iniziali fino all'ottale 377.|

## <a name="comparison-using-the-invariant-culture"></a>Confronto usando la lingua inglese

Per impostazione predefinita, quando il motore delle espressioni regolari esegue confronti senza distinzione fra maiuscole e minuscole, usa le convenzioni sulla combinazione di maiuscole e minuscole delle impostazioni cultura correnti per determinare i caratteri maiuscoli e minuscoli equivalenti.

Tuttavia, questo comportamento risulta inappropriato per alcuni tipi di confronti, in particolare nel caso di confronto di input dell'utente con i nomi di risorse di sistema, ad esempio password, file o URL. Questo scenario è illustrato nell'esempio seguente. Il codice ha lo scopo di bloccare l'accesso a qualsiasi risorsa il cui URL è preceduto da **FILE://**. L'espressione regolare tenta una corrispondenza senza distinzione tra maiuscole e minuscole con la stringa tramite l'espressione regolare `$FILE://`. Tuttavia, quando le impostazioni cultura del sistema correnti sono tr-TR (turco di Turchia), "I" non è l'equivalente maiuscolo di "i". Di conseguenza, la chiamata al metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> restituisce `false` e l'accesso al file è consentito.

[!code-csharp[Conceptual.Regex.Language.Options#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#14)]
[!code-vb[Conceptual.Regex.Language.Options#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#14)]

> [!NOTE]
> Per altre informazioni sui confronti di stringhe che supportano la distinzione tra maiuscole e minuscole e che usano la lingua inglese, vedere [Procedure consigliate per l'uso di stringhe](best-practices-strings.md).

Invece di usare i confronti senza distinzione fra maiuscole e minuscole delle impostazioni cultura correnti, è possibile specificare l'opzione <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType> per ignorare le differenze culturali di lingua e usare le convenzioni della lingua inglese.

> [!NOTE]
> Il confronto usando la lingua inglese è disponibile solo fornendo il valore <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType> al parametro `options` di un costruttore della classe <xref:System.Text.RegularExpressions.Regex> o un metodo statico dei criteri di ricerca. Non è disponibile come opzione inline.

L'esempio che segue è identico al precedente, tranne il fatto che il metodo statico <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> viene chiamato con opzioni che includono <xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant?displayProperty=nameWithType>. Anche quando le impostazioni cultura correnti sono quelle del turco (Turchia), il motore delle espressioni regolari consente di individuare la corrispondenza tra "FILE" e "file" e di bloccare l'accesso alla risorsa del file.

[!code-csharp[Conceptual.Regex.Language.Options#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#15)]
[!code-vb[Conceptual.Regex.Language.Options#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#15)]

## <a name="see-also"></a>Vedere anche

- [Linguaggio di espressioni regolari - Riferimento rapido](regular-expression-language-quick-reference.md)
