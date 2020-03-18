---
title: Costrutti vari nelle espressioni regolari
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
ms.openlocfilehash: a43ce44e11a9231dee2961ee02bac745d9ca71cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141610"
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a>Costrutti vari nelle espressioni regolari
Le espressioni regolari in .NET includono tre costrutti vari di linguaggio. Uno consente di abilitare o disabilitare opzioni di corrispondenza specifiche all'interno di un modello dell'espressione regolare. I restanti due consentono di includere commenti in un'espressione regolare.  
  
## <a name="inline-options"></a>Opzioni inline  
 È possibile impostare o disabilitare opzioni di corrispondenza specifiche del modello per una parte di espressione regolare usando la sintassi  
  
`(?imnsx-imnsx)`  
  
 Elencare le opzioni da abilitare dopo il punto interrogativo e le opzioni da disabilitare dopo il segno di sottrazione. Nella tabella seguente viene descritta ciascuna opzione. Per altre informazioni su ciascuna opzione, vedere [Opzioni di espressioni regolari](../../../docs/standard/base-types/regular-expression-options.md).  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`i`|Corrispondenza senza distinzione tra maiuscole e minuscole.|  
|`m`|Modalità multiriga.|  
|`n`|Solo acquisizioni esplicite. Le parentesi non fungono da gruppi di acquisizione.|  
|`s`|Modalità a riga singola.|  
|`x`|Ignora gli spazi vuoti senza escape e consente commenti in modalità X.|  
  
 Qualsiasi modifica nelle opzioni dell'espressione regolare definita dal costrutto `(?imnsx-imnsx)` rimane attiva fino alla fine del gruppo di inclusione.  
  
> [!NOTE]
> Il `(?imnsx-imnsx:` *costrutto* `)` di raggruppamento delle sottoespressioni fornisce funzionalità identiche per una sottoespressione. Per altre informazioni, vedere [Costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 Nell'esempio seguente vengono usate le opzioni `i`, `n` e `x` per disabilitare la distinzione tra maiuscole e minuscole e abilitare le acquisizioni esplicite, nonché per ignorare lo spazio vuoto nel modello dell'espressione regolare all'interno di un'espressione regolare.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 Nell'esempio vengono definite due espressioni regolari. La prima, `\b(D\w+)\s(d\w+)\b`, corrisponde a due parole consecutive che iniziano con una "D" maiuscola e una "d" minuscola. La seconda espressione regolare, `\b(D\w+)(?ixn) \s (d\w+) \b`, usa opzioni inline per modificare questo modello, come descritto nella tabella seguente. Confrontando i risultati viene confermato l'effetto del costrutto `(?ixn)`.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`(D\w+)`|Trovare la corrispondenza di una "D" maiuscola seguita da uno o più caratteri alfanumerici. Equivale al primo gruppo di acquisizione.|  
|`(?ixn)`|Da questo momento eseguire confronti senza distinzione tra maiuscole e minuscole, eseguire solo acquisizioni esplicite e ignorare gli spazi vuoti nel modello dell'espressione regolare.|  
|`\s`|Trova la corrispondenza con uno spazio vuoto.|  
|`(d\w+)`|Trovare la corrispondenza di una "d" minuscola seguita da uno o più caratteri alfanumerici. Questo gruppo non viene acquisito perché è stata abilitata l'opzione `n` (acquisizione esplicita).|  
|`\b`|Trova la corrispondenza di un confine di parola.|  
  
## <a name="inline-comment"></a>Commento inline  
 Il `(?#` costrutto di *commento* `)` consente di includere un commento inline in un'espressione regolare. Il motore delle espressioni regolari non usa una parte del commento nella corrispondenza tra modelli, anche se il commento è incluso nella stringa restituita dal metodo <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType>. Il commento termina in corrispondenza della prima parentesi chiusa.  
  
 Nell'esempio seguente viene ripetuto il primo criterio dell'espressione regolare dell'esempio nella sezione precedente. Vengono aggiunti due commenti inline all'espressione regolare per indicare se il confronto fa distinzione tra maiuscole e minuscole. Il modello dell'espressione regolare, `\b((?# case-sensitive comparison)D\w+)\s(?ixn)((?#case-insensitive comparison)d\w+)\b`, viene definito nel modo seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`(?# case-sensitive comparison)`|Un commento. Non influisce sul comportamento della corrispondenza tra modelli.|  
|`(D\w+)`|Trovare la corrispondenza di una "D" maiuscola seguita da uno o più caratteri alfanumerici. Equivale al primo gruppo di acquisizione.|  
|`\s`|Trova la corrispondenza con uno spazio vuoto.|  
|`(?ixn)`|Da questo momento eseguire confronti senza distinzione tra maiuscole e minuscole, eseguire solo acquisizioni esplicite e ignorare gli spazi vuoti nel modello dell'espressione regolare.|  
|`(?#case-insensitive comparison)`|Un commento. Non influisce sul comportamento della corrispondenza tra modelli.|  
|`(d\w+)`|Trovare la corrispondenza di una "d" minuscola seguita da uno o più caratteri alfanumerici. Equivale al secondo gruppo di acquisizione.|  
|`\b`|Trova la corrispondenza di un confine di parola.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## <a name="end-of-line-comment"></a>Commento di fine riga  
 Un cancelletto (`#`) contrassegna un commento in modalità X, che inizia in corrispondenza del carattere senza escape # alla fine del modello dell'espressione regolare e continua fino alla fine della riga. Per usare questo costrutto, è necessario abilitare l'opzione `x` (mediante opzioni inline) o specificare il valore <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> per il parametro `option` quando si crea l'istanza dell'oggetto <xref:System.Text.RegularExpressions.Regex> o si chiama un metodo statico <xref:System.Text.RegularExpressions.Regex>.  
  
 L'esempio seguente illustra il costrutto del commento di fine riga. Determina se una stringa è una stringa di formato composito che include almeno un elemento di formato. La tabella seguente descrive i costrutti nel modello dell'espressione regolare:  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`\{`|Trovare la corrispondenza con una parentesi graffa di apertura.|  
|`\d+`|Trova la corrispondenza con una o più cifre decimali.|  
|`(,-*\d+)*`|Trovare la corrispondenza con zero o una occorrenza di una virgola, seguita da un segno di sottrazione, seguito da una o più cifre decimali.|  
|`(\:\w{1,4}?)*`|Trovare la corrispondenza con zero o una occorrenza del segno di due punti, seguito dal numero minimo possibile di caratteri di spazio vuoto tra uno e quattro.|  
|`\}`|Trovare la corrispondenza con una parentesi graffa di chiusura.|  
|`(?x)`|Abilitare l'opzione per ignorare gli spazi vuoti nel modello in modo che il commento di fine riga venga riconosciuto.|  
|`# Looks for a composite format item.`|Un commento di fine riga.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 Si noti che, invece di specificare il costrutto `(?x)` nell'espressione regolare, il commento può anche essere riconosciuto chiamando il metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> e passandogli il valore di enumerazione <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Linguaggio delle espressioni regolari - Guida di riferimento rapidoRegular Expression Language - Quick Reference](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
