---
title: Ancoraggi in espressioni regolari .NET
description: Informazioni su come usare gli ancoraggi nei criteri di espressioni regolari.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- atomic zero-width assertions
- regular expressions, anchors
- regular expressions, atomic zero-width assertions
- anchors, in regular expressions
- metacharacters, atomic zero-width assertions
- metacharacters, anchors
- .NET Framework regular expressions, anchors
- .NET Framework regular expressions, atomic zero-width assertions
ms.assetid: 336391f6-2614-499b-8b1b-07a6837108a7
ms.openlocfilehash: e86bae8a687e89acba9a0b713630b43809f081d1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290629"
---
# <a name="anchors-in-regular-expressions"></a>Ancoraggi in espressioni regolari
Gli ancoraggi, o asserzioni atomiche di larghezza zero, specificano una posizione della stringa in cui deve verificarsi una corrispondenza. Quando si usa un ancoraggio nell'espressione di ricerca, il motore delle espressioni regolari non avanza nella stringa né utilizza caratteri, ma cerca una corrispondenza solo nella posizione specificata. Ad esempio, `^` specifica che la corrispondenza deve iniziare all'inizio di una riga o stringa. Di conseguenza, l'espressione regolare `^http:` considera la corrispondenza "http:" solo quando si verifica all'inizio di una riga. La tabella seguente contiene gli ancoraggi supportati dalle espressioni regolari in .NET.  
  
|Anchor|Descrizione|  
|------------|-----------------|  
|`^`|Per impostazione predefinita, la corrispondenza deve verificarsi all'inizio della stringa; in modalità multiriga, deve verificarsi all'inizio della riga. Per altre informazioni, vedere [Inizio di stringa o riga](#start-of-string-or-line-).|  
|`$`|Per impostazione predefinita, la corrispondenza deve verificarsi alla fine della stringa oppure prima di `\n` alla fine della stringa; in modalità multiriga, deve verificarsi alla fine della riga oppure prima di `\n` alla fine della riga. Per altre informazioni, vedere [Fine di stringa o riga](#end-of-string-or-line-).|  
|`\A`|La corrispondenza deve verificarsi solo all'inizio della stringa (nessun supporto per più righe). Per altre informazioni, vedere [Solo inizio di stringa](#start-of-string-only-a).|  
|`\Z`|La corrispondenza deve verificarsi alla fine della stringa o prima di `\n` alla fine della stringa. Per altre informazioni, vedere [Fine di stringa o prima di terminare una nuova riga](#end-of-string-or-before-ending-newline-z).|  
|`\z`|La corrispondenza deve verificarsi solo alla fine della stringa. Per altre informazioni, vedere [Solo fine di stringa](#end-of-string-only-z).|  
|`\G`|La corrispondenza deve iniziare nella posizione in cui è terminata la corrispondenza precedente. Per altre informazioni, vedere [Corrispondenze contigue](#contiguous-matches-g).|  
|`\b`|La corrispondenza deve verificarsi in un confine di parola. Per altre informazioni, vedere [Confine di parola](#word-boundary-b).|  
|`\B`|La corrispondenza non deve verificarsi in un confine di parola. Per altre informazioni, vedere [Carattere che non costituisce un confine di parola](#non-word-boundary-b).|  

## <a name="start-of-string-or-line-"></a>Inizio di stringa o riga: ^  
 Per impostazione predefinita, l'ancoraggio `^` specifica che il criterio seguente deve iniziare in corrispondenza della posizione del primo carattere della stringa. Se si usa `^` con l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> (vedere [Opzioni di espressioni regolari](regular-expression-options.md)), la corrispondenza deve verificarsi all'inizio di ogni riga.  
  
 L'esempio seguente usa l'ancoraggio `^` in un'espressione regolare che estrae informazioni sugli anni durante i quali sono esistite alcune squadre di baseball professionale. L'esempio chiama due overload del metodo <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>  
  
- La chiamata dell'overload <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29> trova solo la prima sottostringa nella stringa di input corrispondente al criterio di espressione regolare.  
  
- La chiamata dell'overload <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29> con il parametro `options` impostato su <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> trova tutte le cinque sottostringhe.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/startofstring1.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/startofstring1.vb#1)]  
  
 Il criterio di ricerca di espressioni regolari `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+` è definito nel modo illustrato nella tabella seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`^`|La corrispondenza deve iniziare all'inizio della stringa di input (o all'inizio della riga se il metodo viene chiamato con l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> ).|  
|`((\w+(\s?)){2,}`|Trova uno o più caratteri alfanumerici seguiti da nessuno o uno spazio almeno due volte. Equivale al primo gruppo di acquisizione. Questa espressione definisce anche un secondo e un terzo gruppo di acquisizione: il secondo è costituito dalla parola acquisita e il terzo è costituito dallo spazio vuoto acquisito.|  
|`,\s`|Trova una virgola seguita da uno spazio vuoto.|  
|`(\w+\s\w+)`|Trova uno o più caratteri alfanumerici seguiti da uno spazio, seguito da uno o più caratteri alfanumerici. Questo è il quarto gruppo di acquisizione.|  
|`,`|Trova la corrispondenza con una virgola.|  
|`\s\d{4}`|Trova uno spazio seguito da quattro cifre decimali.|  
|<code>(-(\d{4}&#124;present))?</code>|Trova nessuna o una occorrenza di un trattino seguita da quattro cifre decimali o dalla stringa "present". Equivale al sesto gruppo di acquisizione. Include anche un settimo gruppo di acquisizione.|  
|`,?`|Trova nessuna o una occorrenza di una virgola.|  
|<code>(\s\d{4}(-(\d{4}&#124;present))?,?)+</code>|Trova una o più occorrenze di: uno spazio, quattro cifre decimali, nessuna o una occorrenza di un trattino seguita da quattro cifre decimali oppure la stringa "present" e nessuna o una virgola. Equivale al quinto gruppo di acquisizione.|

## <a name="end-of-string-or-line-"></a>Fine di stringa o riga: ^  
 L'ancoraggio `$` specifica che il criterio precedente deve verificarsi alla fine della stringa di input oppure prima di `\n` alla fine della stringa di input.  
  
 Se si usa `$` con l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> , la corrispondenza può verificarsi anche alla fine di una riga. Notare che `$` corrisponde a `\n` , ma non a `\r\n` (combinazione di ritorno a capo e caratteri di nuova riga o CR/LF). Per trovare la combinazione di caratteri CR/LF, includere `\r?$` nel criterio di espressione regolare.  
  
 L'esempio seguente aggiunge l'ancoraggio `$` al criterio di espressione regolare usato nell'esempio della sezione [Inizio di stringa o riga](#start-of-string-or-line-) . Se usato con la stringa di input originale, che include cinque righe di testo, il metodo <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29?displayProperty=nameWithType> non riesce a trovare una corrispondenza, perché la fine della prima riga non corrisponde al criterio `$` . Quando la stringa di input originale viene suddivisa in una matrice di stringhe, il metodo <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29?displayProperty=nameWithType> riesce a trovare la corrispondenza in ognuna delle cinque righe. Quando il metodo <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> viene chiamato con il parametro `options` impostato su <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>, non viene trovata alcuna corrispondenza perché il criterio di espressione regolare non tiene conto dell'elemento di ritorno a capo (\u+000D). Tuttavia, quando il criterio di espressione regolare viene modificato sostituendo `$` con `\r?$`, la chiamata del metodo <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> con il parametro `options` impostato su <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> trova di nuovo cinque corrispondenze.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring1.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring1.vb#2)]

## <a name="start-of-string-only-a"></a>Solo inizio di stringa: \A  
 L'ancoraggio `\A` specifica che la corrispondenza deve verificarsi all'inizio della stringa di input. L'ancoraggio è identico a `^` , ad eccezione del fatto che `\A` ignora l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . Di conseguenza, può trovare solo l'inizio della prima riga in una stringa di input con più righe.  
  
 L'esempio seguente è simile agli esempi per gli ancoraggi `^` e `$` . L'esempio usa l'ancoraggio `\A` in un'espressione regolare che estrae informazioni sugli anni durante i quali sono esistite alcune squadre di baseball professionale. La stringa di input include cinque righe. La chiamata del metodo <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> trova solo la prima sottostringa nella stringa di input corrispondente al criterio di espressione regolare. Come mostrato nell'esempio, l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline> non ha alcun effetto.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/startofstring2.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/startofstring2.vb#3)]

## <a name="end-of-string-or-before-ending-newline-z"></a>Fine di stringa o prima di terminare una nuova riga: \Z  
 L'ancoraggio `\Z` specifica che la corrispondenza deve verificarsi alla fine della stringa di input oppure prima di `\n` alla fine della stringa di input. L'ancoraggio è identico a `$` , ad eccezione del fatto che `\Z` ignora l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . Di conseguenza, in una stringa con più righe può trovare solo la fine dell'ultima riga oppure l'ultima riga prima di `\n`.  
  
 Notare che `\Z` corrisponde a `\n` , ma non a `\r\n` (combinazione di caratteri CR/LF). Per trovare la combinazione di caratteri CR/LF, includere `\r?\Z` nel criterio di espressione regolare.  
  
 L'esempio seguente usa l'ancoraggio `\Z` in un'espressione regolare simile all'esempio della sezione [Inizio di stringa o riga](#start-of-string-or-line-) , che estrae informazioni sugli anni durante i quali sono esistite alcune squadre di baseball professionale. La sottoespressione `\r?\Z` nell'espressione regolare `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z` trova la fine di una stringa e anche una stringa che termina con `\n` o `\r\n`. Di conseguenza, ogni elemento nella matrice corrisponde al criterio di espressione regolare.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring2.cs#4)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring2.vb#4)]

## <a name="end-of-string-only-z"></a>Solo fine di stringa: \z  
 L'ancoraggio `\z` specifica che la corrispondenza deve verificarsi alla fine della stringa di input. Come per l'elemento del linguaggio `$` , `\z` ignora l'opzione <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> . Diversamente dall'elemento del linguaggio `\Z` , `\z` non trova un carattere `\n` alla fine di una stringa. Di conseguenza, può trovare solo l'ultima riga della stringa di input.  
  
 L'esempio seguente usa l'ancoraggio `\z` in un'espressione regolare che è altrimenti identica all'esempio della sezione precedente, che estrae informazioni sugli anni durante i quali sono esistite alcune squadre di baseball professionale. L'esempio prova a trovare ognuno dei cinque elementi in una matrice di stringhe con il criterio di espressione regolare `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z`. Due delle stringhe terminano con caratteri di ritorno a capo e di avanzamento riga, mentre le altre due no. Come mostrato dall'output, solo le stringhe senza carattere di ritorno a capo o avanzamento riga corrispondono al criterio.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring3.cs#5)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring3.vb#5)]

## <a name="contiguous-matches-g"></a>Corrispondenze contigue: \G  
 L'ancoraggio `\G` specifica che la corrispondenza deve verificarsi nel punto in cui è terminata la corrispondenza precedente. Se usato con il metodo <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> , questo ancoraggio garantisce che tutte le corrispondenze siano contigue.  
  
 L'esempio seguente usa un'espressione regolare per estrarre i nomi delle specie di roditori da una stringa con valori delimitati da virgole.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/contiguous1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/contiguous1.vb#6)]  
  
 L'espressione regolare `\G(\w+\s?\w*),?` viene interpretata come illustrato nella tabella seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`\G`|La corrispondenza deve iniziare nel punto in cui termina l'ultima corrispondenza.|  
|`\w+`|Trova la corrispondenza di uno o più caratteri alfanumerici.|  
|`\s?`|Trova nessuno o uno spazio.|  
|`\w*`|Trova la corrispondenza di zero o più caratteri alfanumerici.|  
|`(\w+\s?\w*)`|Trova uno o più caratteri alfanumerici seguiti da nessuno o uno spazio, seguito da nessuno o più caratteri alfanumerici. Equivale al primo gruppo di acquisizione.|  
|`,?`|Trova nessuna o una occorrenza di un carattere virgola letterale.|

## <a name="word-boundary-b"></a>Confine di parola: \b  
 L'ancoraggio `\b` specifica che la corrispondenza deve verificarsi in un confine tra un carattere alfanumerico (elemento del linguaggio `\w` ) e uno non alfanumerico (elemento del linguaggio `\W` ). I caratteri alfanumerici sono costituiti da lettere, cifre e caratteri di sottolineatura. Un carattere non alfanumerico è qualsiasi carattere diverso da lettere, cifre e carattere di sottolineatura. Per ulteriori informazioni, vedere [classi di caratteri](character-classes-in-regular-expressions.md). La corrispondenza può verificarsi anche su un confine di parola all'inizio o alla fine della stringa.  
  
 L'ancoraggio `\b` viene usato di frequente per garantire che una sottoespressione corrisponda a un'intera parola anziché solo all'inizio o alla fine di una parola. L'espressione regolare `\bare\w*\b` nell'esempio seguente mostra questo utilizzo. L'espressione trova qualsiasi parola che inizia con la sottostringa "are". L'output dell'esempio mostra anche che `\b` trova sia l'inizio sia la fine della stringa di input.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/word1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/word1.vb#7)]  
  
 Il criterio di ricerca di espressioni regolari viene interpretato come illustrato nella tabella seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia la corrispondenza sul confine di parola.|  
|`are`|Trova la sottostringa "are".|  
|`\w*`|Trova la corrispondenza di zero o più caratteri alfanumerici.|  
|`\b`|Termina la corrispondenza sul confine di parola.|  

## <a name="non-word-boundary-b"></a>Carattere che non costituisce un confine di parola: \B  
 L'ancoraggio `\B` specifica che la corrispondenza non deve verificarsi in un confine di parola. Si tratta dell'effetto contrario rispetto all'ancoraggio `\b` .  
  
 L'esempio seguente usa l'ancoraggio `\B` per individuare le occorrenze della sottostringa "qu" in una parola. Il criterio di espressione regolare `\Bqu\w+` trova una sottostringa che inizia con "qu" che non si trova all'inizio di una parola e che continua fino alla fine della parola.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/nonword1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/nonword1.vb#8)]  
  
 Il criterio di ricerca di espressioni regolari viene interpretato come illustrato nella tabella seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`\B`|La corrispondenza non deve iniziare nel confine di parola.|  
|`qu`|Trova la sottostringa "qu".|  
|`\w+`|Trova la corrispondenza di uno o più caratteri alfanumerici.|  
  
## <a name="see-also"></a>Vedere anche

- [Linguaggio di espressioni regolari - Riferimento rapido](regular-expression-language-quick-reference.md)
- [Opzioni di espressione regolare](regular-expression-options.md)
