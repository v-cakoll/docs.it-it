---
title: quantificatori in espressioni regolari
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, quantifiers
- metacharacters, quantifiers
- minimal matching quantifiers
- quantifiers in regular expressions
- .NET Framework regular expressions, quantifiers
- quantifiers
- lazy quantifiers
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab06aa0c331c8cbd4c8986cced29334046f30264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="quantifiers-in-regular-expressions"></a>quantificatori in espressioni regolari
I quantificatori specificano il numero di istanze di un carattere, un gruppo o una classe di caratteri che deve essere presente nell'input affinché venga trovata una corrispondenza.  Nella tabella seguente vengono elencati i quantificatori supportati da .NET.  
  
|Quantificatore greedy|Quantificatore lazy|Descrizione|  
|-----------------------|---------------------|-----------------|  
|`*`|`*?`|Trova la corrispondenza zero o più volte.|  
|`+`|`+?`|Trova la corrispondenza una o più volte.|  
|`?`|`??`|Trova la corrispondenza zero o una volta.|  
|`{` *n* `}`|`{` *n* `}?`|Corrisponde esattamente  *n*  volte.|  
|`{` *n* `,}`|`{` *n* `,}?`|Corrispondono ad almeno  *n*  volte.|  
|`{` *n* `,` *m* `}`|`{` *n* `,` *m* `}?`|Ottiene una corrispondenza da  *n*  a *m* volte.|  
  
 Le quantità `n` e `m` sono costanti integer. In genere, i quantificatori sono greedy: il motore delle espressioni regolari trova la corrispondenza con il maggior numero possibile di determinati criteri. L'aggiunta del carattere `?` rende un quantificatore lazy: il motore delle espressioni regolari trova la corrispondenza con il minor numero possibile di occorrenze. Per una descrizione completa della differenza tra quantificatori greedy e lazy, vedere la sezione [Quantificatori greedy e lazy](#Greedy) più avanti in questo argomento.  
  
> [!IMPORTANT]
>  Annidare i quantificatori, come nel caso del criterio di espressione regolare `(a*)*`, può aumentare il numero dei confronti che deve eseguire il motore delle espressioni regolari, come una funzione esponenziale del numero di caratteri nella stringa di input. Per ulteriori informazioni su questo comportamento e relative soluzioni alternative, vedere [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).  
  
## <a name="regular-expression-quantifiers"></a>Quantificatori delle espressioni regolari  
 Nelle sezioni seguenti sono riportati i quantificatori supportati dalle espressioni regolari in .NET.  
  
> [!NOTE]
>  Se il *, +,?, {, e} sono presenti caratteri in un modello di espressione regolare, il motore delle espressioni regolari li interpreta come quantificatori o parte di costrutti del quantificatore a meno che non sono inclusi in un [classe di caratteri](../../../docs/standard/base-types/character-classes-in-regular-expressions.md). Per interpretarli come caratteri letterali all'esterno di una classe di caratteri, è necessaria una sequenza di escape con i caratteri preceduti da una barra rovesciata. Ad esempio, la stringa `\*` in un'espressione regolare modello viene interpretato come un asterisco letterale ("\*") caratteri.  
  
### <a name="match-zero-or-more-times-"></a>Trova la corrispondenza zero o più volte: *  
 Il quantificatore `*` trova la corrispondenza con l'elemento precedente zero o più volte. È equivalente al `{0,}` quantificatore. `*`è un quantificatore greedy il cui equivalente lazy è `*?`.  
  
 L'esempio seguente illustra questa espressione regolare. Delle nove cifre nella stringa di input, cinque corrispondono al criterio e quattro (`95`, `929`, `9129` e `9919`) no.  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`91*`|Trova un "9" seguito da zero o più caratteri "1".|  
|`9*`|Trova la corrispondenza con zero o più caratteri "9".|  
|`\b`|Terminare al confine di una parola.|  
  
### <a name="match-one-or-more-times-"></a>Trova la corrispondenza una o più volte: +  
 Il `+` quantificatore corrisponde all'elemento precedente una o più volte. È equivalente a `{1,}`. `+`è un quantificatore greedy il cui equivalente lazy è `+?`.  
  
 Ad esempio, l'espressione regolare `\ban+\w*?\b` tenta di trovare la corrispondenza con intere parole che iniziano con la lettera `a` seguita da una o più istanze della lettera `n`. L'esempio seguente illustra questa espressione regolare. L'espressione regolare trova le parole `an`, `annual`, `announcement`, `antique` e, correttamente, non riesce a trovare `autumn` e `all`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`an+`|Trova una "a" seguita da uno o più caratteri "n".|  
|`\w*?`|Trova la corrispondenza con un carattere alfanumerico o più volte, ma il minor numero di volte possibile.|  
|`\b`|Terminare al confine di una parola.|  
  
### <a name="match-zero-or-one-time-"></a>Trova la corrispondenza zero o una volta: ?  
 Il `?` quantificatore corrisponde il precedente elemento zero o una volta. È equivalente a `{0,1}`. `?`è un quantificatore greedy il cui equivalente lazy è `??`.  
  
 Ad esempio, l'espressione regolare `\ban?\b` tenta di trovare la corrispondenza con intere parole che iniziano con la lettera `a` seguita da zero o una istanza della lettera `n`. In altre parole, tenta di trovare la corrispondenza con le parole `a` e `an`. L'esempio seguente illustra questa espressione regolare.  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`an?`|Trova una "a" seguita da zero o un carattere "n".|  
|`\b`|Terminare al confine di una parola.|  
  
### <a name="match-exactly-n-times-n"></a>Trova la corrispondenza esatta n volte: {n}  
 Il `{`  *n*  `}` quantificatore corrisponde all'elemento precedente esattamente  *n*  volte, dove  *n* è qualsiasi numero intero. `{`*n*`}`è un quantificatore greedy il cui equivalente lazy è `{`  *n*  `}?`.  
  
 Ad esempio, l'espressione regolare `\b\d+\,\d{3}\b` tenta di trovare la corrispondenza con il confine di una parola seguito da una o più cifre decimali seguite da tre cifre decimali seguite dal confine di una parola. L'esempio seguente illustra questa espressione regolare.  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`\d+`|Trova la corrispondenza con una o più cifre decimali.|  
|`\,`|Trova la corrispondenza con un carattere virgola.|  
|`\d{3}`|Trova la corrispondenza con tre cifre decimali.|  
|`\b`|Terminare al confine di una parola.|  
  
### <a name="match-at-least-n-times-n"></a>Trova la corrispondenza almeno n volte: {n,}  
 Il `{`  *n*  `,}` quantificatore corrisponde all'elemento precedente almeno  *n*  volte, dove  *n* è qualsiasi numero intero. `{`*n*`,}`è un quantificatore greedy il cui equivalente lazy è `{`  *n*  `}?`.  
  
 Ad esempio, l'espressione regolare `\b\d{2,}\b\D+` tenta di trovare la corrispondenza con il confine di una parola seguito da almeno due cifre seguite dal confine di una parola e un carattere non numerico. L'esempio seguente illustra questa espressione regolare. L'espressione regolare non riesce a trovare la frase `"7 days"` perché contiene una sola cifra decimale, ma corrisponde correttamente le frasi `"10 weeks and 300 years"`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`\d{2,}`|Trova la corrispondenza con almeno due cifre decimali.|  
|`\b`|Trova la corrispondenza di un confine di parola.|  
|`\D+`|Trova la corrispondenza con almeno una cifra non decimale.|  
  
### <a name="match-between-n-and-m-times-nm"></a>Trova la corrispondenza tra n e m volte: {n,m}  
 Il `{`  *n*  `,` *m* `}` quantificatore corrisponde all'elemento precedente almeno  *n*  volte, ma non più di *m* volte, dove  *n*  e *m* sono numeri interi. `{`*n*`,`*m* `}` è un quantificatore greedy il cui equivalente lazy è `{`  *n*  `,` *m*`}?`.  
  
 Nell'esempio seguente, l'espressione regolare `(00\s){2,4}` tenta di trovare una corrispondenza tra due e quattro occorrenze di due cifre zero seguite da uno spazio. Si noti che la parte finale della stringa di input include questo criterio cinque volte anziché il numero massimo di quattro. Tuttavia, solo la parte iniziale della sottostringa (fino allo spazio e alla quinta coppia di zeri) corrisponde al criterio dell'espressione regolare.  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### <a name="match-zero-or-more-times-lazy-match-"></a>Trova la corrispondenza zero o più volte (corrispondenza lazy): *?  
 Il `*?` quantificatore corrisponde all'elemento precedente zero o più volte, ma il minor numero di volte possibile. È un quantificatore lazy omologo del quantificatore greedy `*`.  
  
 Nell'esempio seguente l'espressione regolare `\b\w*?oo\w*?\b` corrisponde a tutte le parole contenenti la stringa `oo`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`\w*?`|Trova la corrispondenza con zero o più caratteri alfanumerici, ma il minor numero di caratteri possibile.|  
|`oo`|Trova la corrispondenza con la stringa "oo".|  
|`\w*?`|Trova la corrispondenza con zero o più caratteri alfanumerici, ma il minor numero di caratteri possibile.|  
|`\b`|Termina al confine di una parola.|  
  
### <a name="match-one-or-more-times-lazy-match-"></a>Trova la corrispondenza una o più volte (corrispondenza lazy): +?  
 Il `+?` quantificatore corrisponde all'elemento precedente una o più volte, ma il minor numero di volte possibile. È un quantificatore lazy omologo del quantificatore greedy `+`.  
  
 Ad esempio, l'espressione regolare `\b\w+?\b` trova la corrispondenza con uno o più caratteri separati confini di parole. L'esempio seguente illustra questa espressione regolare.  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### <a name="match-zero-or-one-time-lazy-match-"></a>Trova la corrispondenza zero o una volta (corrispondenza lazy): ??  
 Il `??` quantificatore corrisponde all'elemento precedente zero o una volta, ma il minor numero di volte possibile. È un quantificatore lazy omologo del quantificatore greedy `?`.  
  
 Ad esempio, l'espressione regolare `^\s*(System.)??Console.Write(Line)??\(??` tenta di trovare la corrispondenza con le stringhe "Console.Write" o "Console.WriteLine". La stringa può anche includere "System." prima di "Console" e può essere seguita da una parentesi di apertura. La stringa deve essere all'inizio di una riga, anche se può essere preceduta da uno spazio vuoto. L'esempio seguente illustra questa espressione regolare.  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`^`|Trova la corrispondenza con l'inizio del flusso di input.|  
|`\s*`|Trovare la corrispondenza di zero o più spazi vuoti.|  
|`(System.)??`|Trova la corrispondenza con zero o una occorrenza della stringa "System.".|  
|`Console.Write`|Trova la corrispondenza con la stringa "Console.Write".|  
|`(Line)??`|Trova la corrispondenza con zero o una occorrenza della stringa "Line".|  
|`\(??`|Trova la corrispondenza con zero o una occorrenza della parentesi di apertura.|  
  
### <a name="match-exactly-n-times-lazy-match-n"></a>Trova la corrispondenza esatta n volte (corrispondenza lazy): {n}?  
 Il `{`  *n*  `}?` quantificatore corrisponde all'elemento precedente esattamente `n` volte, dove  *n*  è qualsiasi numero intero. È un quantificatore lazy omologo del quantificatore greedy `{`  *n*  `}+`.  
  
 Nell'esempio seguente viene usata l'espressione regolare `\b(\w{3,}?\.){2}?\w{3,}?\b` per identificare un indirizzo di sito Web. Si noti che corrisponde a "www.microsoft.com" e "msdn.microsoft.com", ma non a "mywebsite" o "mycompany.com".  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`(\w{3,}?\.)`|Trova la corrispondenza con almeno 3 caratteri alfanumerici, ma il minor numero di caratteri possibile, seguiti da un carattere punto. Equivale al primo gruppo di acquisizione.|  
|`(\w{3,}?\.){2}?`|Corrisponde al criterio nel primo gruppo due volte, ma il minor numero di volte possibile.|  
|`\b`|Termina la corrispondenza sul confine di parola.|  
  
### <a name="match-at-least-n-times-lazy-match-n"></a>Trova la corrispondenza almeno n volte (corrispondenza lazy): {n,}?  
 Il `{`  *n*  `,}?` quantificatore corrisponde all'elemento precedente almeno `n` volte, dove  *n*  è qualsiasi numero intero, ma il minor numero di volte possibili. È un quantificatore lazy omologo del quantificatore greedy `{`  *n*  `,}`.  
  
 Vedere l'esempio per il `{`  *n*  `}?` quantificatore nella sezione precedente per un'illustrazione. L'espressione regolare in questo esempio viene utilizzato il `{`  *n*  `,}` quantificatore per confrontare una stringa che contiene almeno tre caratteri seguiti da un punto.  
  
### <a name="match-between-n-and-m-times-lazy-match-nm"></a>Trova la corrispondenza tra n e m volte (corrispondenza lazy): {n,m}?  
 Il `{`  *n*  `,` *m* `}?` quantificatore corrisponde all'elemento precedente tra `n` e `m` volte, dove  *n*  e *m* sono numeri interi, ma il minor numero di volte possibile. È un quantificatore lazy omologo del quantificatore greedy `{`  *n*  `,` *m*`}`.  
  
 Nell'esempio seguente l'espressione regolare `\b[A-Z](\w*\s+){1,10}?[.!?]` corrisponde alle frasi che contengono da una a dieci parole. Trova la corrispondenza con tutte le frasi nella stringa di input, ad eccezione di una frase che contiene 18 parole.  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`[A-Z]`|Trova la corrispondenza con un carattere maiuscolo da A a Z.|  
|`(\w*\s+)`|Trova la corrispondenza con uno o più caratteri alfanumerici seguiti da uno o più caratteri spazio vuoto. Equivale al primo gruppo di acquisizione.|  
|`{1,10}?`|Trova la corrispondenza con il criterio precedente da 1 a 10 volte, ma il minor numero di volte possibile.|  
|`[.!?]`|Trova la corrispondenza con uno dei caratteri di punteggiatura ".", "!" o "?".|  
  
<a name="Greedy"></a>   
## <a name="greedy-and-lazy-quantifiers"></a>Quantificatori greedy e lazy  
 Alcuni quantificatori hanno due versioni:  
  
-   Una versione greedy.  
  
     Un quantificatore greedy tenta di trovare la corrispondenza con un elemento il maggior numero di volte possibile.  
  
-   Una versione non-greedy (o lazy).  
  
     Un quantificatore non greedy tenta di trovare la corrispondenza con un elemento il minor numero di volte possibile. È possibile trasformare un quantificatore greedy in un quantificatore lazy aggiungendo semplicemente un `?`.  
  
 Si consideri un'espressione regolare semplice progettata per estrarre le ultime quattro cifre da una stringa di numeri, ad esempio un numero di carta di credito. La versione dell'espressione regolare che usa il `*` quantificatore greedy è `\b.*([0-9]{4})\b`. Se tuttavia una stringa contiene due numeri, come illustrato nell'esempio seguente, l'espressione regolare trova la corrispondenza solo con le ultime quattro cifre secondo numero.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 L'espressione regolare non riesce a trovare il primo numero perché il `*` quantificatore tenta di far corrispondere l'elemento precedente il numero di volte possibile nell'intera stringa e quindi trova la corrispondenza alla fine della stringa.  
  
 Questo non è il comportamento desiderato. In alternativa, è possibile utilizzare il `*?`per estrarre cifre da entrambi i numeri, come illustrato nell'esempio seguente.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 Nella maggior parte dei casi le espressioni regolari con quantificatori greedy e lazy restituiscono le stesse corrispondenze. In genere restituiscono risultati diversi quando vengono utilizzati con il carattere jolly (`.`) metacaratteri, che corrisponde a qualsiasi carattere.  
  
## <a name="quantifiers-and-empty-matches"></a>Quantificatori e corrispondenze vuote  
 I quantificatori `*`, `+`, e `{`  *n*  `,` *m* `}` e le controparti lazy si ripetono mai dopo vuota corrispondenza quando il numero minimo di acquisizioni è stato trovato. Questa regola impedisce ai quantificatori di avviare cicli infiniti su corrispondenze di sottoespressioni vuote quando il numero massimo di acquisizioni possibili per il gruppo possibili è infinito o quasi infinito.  
  
 Ad esempio, il codice seguente viene illustrato il risultato di una chiamata al <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> metodo con modello di espressione regolare `(a?)*`, che corrisponde a zero o un carattere "a" zero o più volte. Si noti che il singolo gruppo di acquisizione acquisisce ogni "a", nonché <xref:System.String.Empty?displayProperty=nameWithType>, ma che non è presente alcuna corrispondenza vuota secondo, perché la prima corrispondenza vuota induce il quantificatore a terminare la ripetizione.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 Per vedere in pratica la differenza tra un gruppo di acquisizione che definisce un numero minimo e massimo di acquisizioni e uno che definisce un numero fisso di acquisizioni, considerare i criteri di espressione regolare `(a\1|(?(1)\1)){0,2}` e `(a\1|(?(1)\1)){2}`. Entrambe le espressioni regolari sono costituite da un singolo gruppo di acquisizione, definito come illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`(a\1`|Trova la corrispondenza con "a" insieme al valore del primo gruppo acquisito...|  
|`&#124;(?(1)`|… o verifica se è stato definito il primo gruppo acquisito. (Si noti che il `(?(1)` costrutto non definisce un gruppo di acquisizione.)|  
|`\1))`|Se il primo gruppo acquisito esiste, trovare la corrispondenza con il relativo valore. Se il gruppo non esiste, il gruppo corrisponderà <xref:System.String.Empty?displayProperty=nameWithType>.|  
  
 La prima espressione regolare tenta di trovare la corrispondenza con questo criterio da zero a due volte, la seconda esattamente due volte. Poiché il primo modello raggiunge il numero minimo di acquisizioni con l'acquisizione del primo <xref:System.String.Empty?displayProperty=nameWithType>, mai si ripete per cercare una corrispondenza `a\1`; `{0,2}` quantificatore consente solo corrispondenze vuote nell'ultima iterazione. Al contrario, la seconda espressione regolare trova la corrispondenza con "a" perché restituisce `a\1` una seconda volta. Il numero minimo di iterazioni, 2, impone al motore la ripetizione dopo una corrispondenza vuota.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Linguaggio di espressioni regolari - Riferimento rapido](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)
