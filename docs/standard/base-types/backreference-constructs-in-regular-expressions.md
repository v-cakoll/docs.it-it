---
title: Costrutti di backreference nelle espressioni regolari .NET
description: Informazioni su come identificare gli elementi di testo ripetuti usando i costrutti di backreference in un'espressione regolare.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
ms.openlocfilehash: 905578d763ebe5d5b8eb96a9056fbe11fbfab137
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711532"
---
# <a name="backreference-constructs-in-regular-expressions"></a>Costrutti di backreference nelle espressioni regolari

I backreference sono uno strumento utile per identificare un carattere ripetuto o una sottostringa all'interno di una stringa. Se la stringa di input contiene ad esempio più occorrenze di una sottostringa arbitraria, è possibile trovare la prima occorrenza con un gruppo di acquisizione e usare un backreference per trovare le occorrenze successive della sottostringa.

> [!NOTE]
> Per fare riferimento a gruppi di acquisizione denominati e numerati in stringhe sostitutive, si usa una sintassi separata. Per altre informazioni, vedere [Sostituzioni](substitutions-in-regular-expressions.md).

.NET definisce elementi di linguaggio separati per fare riferimento a gruppi di acquisizione denominati e numerati. Per altre informazioni sui gruppi di acquisizione, vedere [Costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

## <a name="numbered-backreferences"></a>Backreference numerati

Nei backreference numerati si usa la sintassi seguente:

`\`*numero*

dove *numero* è la posizione corretta del gruppo di acquisizione nell'espressione regolare. Ad esempio, `\4` corrisponde al contenuto del quarto gruppo di acquisizione. Se nel modello di espressione regolare *numero* non è definito, si verifica un errore di analisi e il motore delle espressioni regolari genera un'eccezione <xref:System.ArgumentException>. Ad esempio, l'espressione regolare `\b(\w+)\s\1` è valida, poiché `(\w+)` è il primo e l'unico gruppo di acquisizione nell'espressione. D'altra parte, `\b(\w+)\s\2` non è un'espressione valida e genera un'eccezione di argomento, perché non esistono gruppi di acquisizione numerati `\2`. Inoltre, se *numero* identifica un gruppo di acquisizione in una determinata posizione ordinale, ma a tale gruppo di acquisizione è stato assegnato un valore numerico diverso dalla relativa posizione ordinale, il parser delle espressioni regolari genera anche un'eccezione <xref:System.ArgumentException>.

Si noti l'ambiguità tra i codici di escape ottale, ad esempio `\16`, e i backreference `\`*numero* che usano la stessa notazione. Questa ambiguità viene risolta nel modo seguente:

- Le espressioni da `\1` a `\9` vengono sempre interpretate come backreference e non come codici ottali.

- Se la prima cifra di un'espressione composta da più cifre è 8 o 9, ad esempio `\80` o `\91`, l'espressione viene interpretata come valore letterale.

- Le espressioni con numerazione a partire da `\10` vengono considerate backreference se esiste un backreference a tale numero; in caso contrario, vengono interpretate come codici ottali.

- Se l'espressione regolare contiene un backreference a un numero di gruppo non definito, si verifica un errore di analisi e il motore delle espressioni regolari genera un'eccezione <xref:System.ArgumentException>.

Se l'ambiguità è un problema, è possibile utilizzare la notazione del `\k<` *nome,* `>` che non è ambigua e non può essere confusa con codici di carattere ottali. Analogamente, i codici esadecimale come `\xdd` non sono ambigui e non possono essere confusi con backreference.

L'esempio seguente consente di trovare caratteri alfanumerici doppi all'interno di una stringa. Viene definita un'espressione regolare `(\w)\1` costituita dagli elementi seguenti.

|Elemento|Descrizione|
|-------------|-----------------|
|`(\w)`|Trova la corrispondenza di un carattere alfanumerico e la assegna al primo gruppo di acquisizione.|
|`\1`|Trova la corrispondenza del carattere successivo, uguale al valore del primo gruppo di acquisizione.|

[!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
[!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]

## <a name="named-backreferences"></a>Backreference denominati

Per definire un backreference denominato, usare la sintassi seguente:

`\k<`*nome*`>`

oppure:

`\k'`*nome*`'`

dove *nome* è il nome di un gruppo di acquisizione definito nel modello di espressione regolare. Se nel modello di espressione regolare *nome* non è definito, si verifica un errore di analisi e il motore delle espressioni regolari genera un'eccezione <xref:System.ArgumentException>.

L'esempio seguente consente di trovare caratteri alfanumerici doppi all'interno di una stringa. Viene definita un'espressione regolare `(?<char>\w)\k<char>` costituita dagli elementi seguenti.

|Elemento|Descrizione|
|-------------|-----------------|
|`(?<char>\w)`|Trova la corrispondenza di un carattere alfanumerico e la assegna a un gruppo di acquisizione denominato `char`.|
|`\k<char>`|Trova la corrispondenza del carattere successivo, uguale al valore del gruppo di acquisizione denominato `char`.|

[!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
[!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]

## <a name="named-numeric-backreferences"></a>Backreference numerici denominati

In un backreference denominato con `\k`, *nome* può anche essere la rappresentazione stringa di un numero. Nell'esempio seguente viene usata l'espressione regolare `(?<2>\w)\k<2>` per trovare caratteri alfanumerici doppi all'interno di una stringa. In questo caso, l'esempio definisce un gruppo di acquisizione denominato "2" in modo esplicito e conseguentemente il backreference è denominato "2".

[!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
[!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]

Se *nome* è la rappresentazione stringa di un numero e nessun gruppo di acquisizione ha tale nome, `\k<`*nome*`>` corrisponde al `\`*numero* del backreference, dove *numero* è la posizione ordinale dell'acquisizione. Nell'esempio seguente, è presente un solo gruppo di acquisizione denominato `char`. Il costrutto del backreference fa riferimento a tale gruppo come `\k<1>`. Come dimostra l'output dell'esempio, la chiamata a <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> ha esito positivo perché `char` è il primo gruppo di acquisizione.

[!code-csharp[Ordinal.Backreference](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference6.cs)]
[!code-vb[Ordinal.BackReference](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference6.vb)]

Tuttavia, se *nome* è la rappresentazione stringa di un numero e al gruppo di acquisizione in tale posizione è stato assegnato in modo esplicito un nome numerico, il parser delle espressioni regolari non è in grado di identificare il gruppo di acquisizione in base alla posizione ordinale. Al contrario, <xref:System.ArgumentException>genera un file . L'unico gruppo di acquisizione nell'esempio seguente è denominato "2". Dato che il costrutto `\k` viene usato per definire un backreference denominato "1", il parser delle espressioni regolari non è in grado di identificare il primo gruppo di acquisizione e genera un'eccezione.

[!code-csharp[Ordinal.Backreference](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference7.cs)]
[!code-vb[Ordinal.BackReference](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference7.vb)]

## <a name="what-backreferences-match"></a>Corrispondenza dei backreference

Un backreference fa riferimento alla definizione più recente di un gruppo, vale a dire alla definizione all'estrema sinistra, in caso di corrispondenza da sinistra a destra. Quando un gruppo esegue più acquisizioni, un backreference fa riferimento all'acquisizione più recente.

L'esempio seguente include un modello di espressione regolare `(?<1>a)(?<1>\1b)*`, che ridefinisce il gruppo denominato \1. Nella tabella seguente sono descritti i modelli di espressione regolare.

|Modello|Descrizione|
|-------------|-----------------|
|`(?<1>a)`|Trova la corrispondenza del carattere "a" e assegna il risultato al gruppo di acquisizione denominato `1`.|
|`(?<1>\1b)*`|Trova 0 o più occorrenze del gruppo denominato `1` con una "b" e assegna il risultato al gruppo di acquisizione denominato `1`.|

[!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
[!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]

Confrontando l'espressione regolare con la stringa di input ("aababb"), il motore delle espressioni regolari esegue le operazioni seguenti:

1. Parte dall'inizio della stringa e trova una corrispondenza per "a" con l'espressione `(?<1>a)`. Il valore del `1` gruppo è ora "a".

2. Passa al secondo carattere e trova una corrispondenza per la stringa "ab" con l'espressione `\1b` o "ab". Assegna il risultato "ab" a `\1`.

3. Passa al quarto carattere. Per l'espressione `(?<1>\1b)*` la corrispondenza individuata deve essere zero o più volte, ai fini di una corrispondenza corretta della stringa "abb" con l'espressione `\1b`. Assegna il risultato "abb" nuovamente a `\1`.

In questo esempio `*` è un quantificatore di cicli, vale a dire che viene eseguito ripetutamente finché il motore delle espressioni regolari non trova una corrispondenza con il modello che definisce. I quantificatori di cicli non cancellano le definizioni di gruppi.

Se un gruppo non ha acquisito alcuna sottostringa, un backreference a tale gruppo risulterà non definito e non troverà mai corrispondenza. Questo comportamento è illustrato dal modello delle espressioni regolari `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, definito nel modo seguente:

|Modello|Descrizione|
|-------------|-----------------|
|`\b`|Inizia la corrispondenza sul confine di parola.|
|`(\p{Lu}{2})`|Trova la corrispondenza di due maiuscole. Equivale al primo gruppo di acquisizione.|
|`(\d{2})?`|Trova la corrispondenza di zero o di una occorrenza di due cifre decimali. Equivale al secondo gruppo di acquisizione.|
|`(\p{Lu}{2})`|Trova la corrispondenza di due maiuscole. Equivale al terzo gruppo di acquisizione.|
|`\b`|Termina la corrispondenza sul confine di parola.|

Una stringa di input può corrispondere a questa espressione regolare, anche se le due cifre decimali definite dal secondo gruppo di acquisizione non sono presenti. L'esempio seguente illustra che, nonostante una corrispondenza corretta, viene individuato un gruppo di acquisizione vuoto tra due gruppi di acquisizione con corrispondenza corretta.

[!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
[!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]

## <a name="see-also"></a>Vedere anche

- [Linguaggio delle espressioni regolari - Guida di riferimento rapidoRegular Expression Language - Quick Reference](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
