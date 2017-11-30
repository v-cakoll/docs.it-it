---
title: Costrutti vari nelle espressioni regolari
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
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b33d196a7af9bc5a1f81c1624bbd98fea074319
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a>Costrutti vari nelle espressioni regolari
Le espressioni regolari in .NET includono tre costrutti vari di linguaggio. Uno consente di abilitare o disabilitare opzioni di corrispondenza specifiche all'interno di un modello dell'espressione regolare. I restanti due consentono di includere commenti in un'espressione regolare.  
  
## <a name="inline-options"></a>Opzioni inline  
 È possibile impostare o disabilitare opzioni di corrispondenza specifiche del modello per una parte di espressione regolare usando la sintassi  
  
```  
(?imnsx-imnsx)  
```  
  
 Elencare le opzioni da abilitare dopo il punto interrogativo e le opzioni da disabilitare dopo il segno di sottrazione. Nella tabella seguente viene descritta ciascuna opzione. Per altre informazioni su ciascuna opzione, vedere [Opzioni di espressioni regolari](../../../docs/standard/base-types/regular-expression-options.md).  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`i`|Corrispondenza senza distinzione tra maiuscole e minuscole.|  
|`m`|Modalità multiriga.|  
|`n`|Solo acquisizioni esplicite. Le parentesi non fungono da gruppi di acquisizione.|  
|`s`|Modalità a riga singola.|  
|`x`|Ignora gli spazi vuoti senza escape e consente commenti in modalità X.|  
  
 Qualsiasi modifica nelle opzioni di espressione regolare definito dal `(?imnsx-imnsx)` costruire rimane attivo fino alla fine del gruppo di inclusione.  
  
> [!NOTE]
>  Il `(?imnsx-imnsx:` *sottoespressione* `)` costrutto di raggruppamento fornisce funzionalità identiche per una sottoespressione. Per altre informazioni, vedere [Costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 L'esempio seguente usa il `i`, `n`, e `x` opzioni per abilitare tra maiuscole e minuscole e le acquisizioni esplicite e per ignorare gli spazi vuoti nel criterio di espressione regolare all'interno di un'espressione regolare.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 Nell'esempio vengono definite due espressioni regolari. La prima, `\b(D\w+)\s(d\w+)\b`, corrisponde a due parole consecutive che iniziano con una "D" maiuscola e una "d" minuscola. La seconda espressione regolare, `\b(D\w+)(?ixn) \s (d\w+) \b`, usa opzioni inline per modificare questo modello, come descritto nella tabella seguente. Confrontando i risultati viene confermato l'effetto del costrutto `(?ixn)`.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia dal confine di una parola.|  
|`(D\w+)`|Trovare la corrispondenza di una "D" maiuscola seguita da uno o più caratteri alfanumerici. Equivale al primo gruppo di acquisizione.|  
|`(?ixn)`|Da questo momento eseguire confronti senza distinzione tra maiuscole e minuscole, eseguire solo acquisizioni esplicite e ignorare gli spazi vuoti nel modello dell'espressione regolare.|  
|`\s`|Trova la corrispondenza con uno spazio vuoto.|  
|`(d\w+)`|Trovare la corrispondenza di una "d" minuscola seguita da uno o più caratteri alfanumerici. Questo gruppo non viene acquisito in quanto il `n` è stata abilitata l'opzione (acquisizione esplicita)...|  
|`\b`|Trova la corrispondenza di un confine di parola.|  
  
## <a name="inline-comment"></a>Commento inline  
 Il `(?#` *commento* `)` costrutto consente di includere un commento inline in un'espressione regolare. Il motore delle espressioni regolari Usa qualsiasi parte del commento nella corrispondenza, anche se il commento è incluso nella stringa restituita dal <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> metodo. Il commento termina in corrispondenza della prima parentesi chiusa.  
  
 Nell'esempio seguente viene ripetuto il primo criterio dell'espressione regolare dell'esempio nella sezione precedente. Vengono aggiunti due commenti inline all'espressione regolare per indicare se il confronto fa distinzione tra maiuscole e minuscole. Il modello dell'espressione regolare, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, viene definito nel modo seguente.  
  
|Criterio|Descrizione|  
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
 Un simbolo di cancelletto (`#`) contrassegna un commento in modalità x, che inizia in corrispondenza del carattere di escape # alla fine del criterio di espressione regolare e continua fino alla fine della riga. Per utilizzare questo costrutto, è necessario attivare il `x` opzione (tramite le opzioni inline) o specificare il <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> valore per il `option` parametro quando si crea il <xref:System.Text.RegularExpressions.Regex> oggetto o la chiamata a un valore statico <xref:System.Text.RegularExpressions.Regex> metodo.  
  
 L'esempio seguente illustra il costrutto del commento di fine riga. Determina se una stringa è una stringa di formato composito che include almeno un elemento di formato. La tabella seguente descrive i costrutti nel modello dell'espressione regolare:  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\{`|Trovare la corrispondenza con una parentesi graffa di apertura.|  
|`\d+`|Trova la corrispondenza con una o più cifre decimali.|  
|`(,-*\d+)*`|Trovare la corrispondenza con zero o una occorrenza di una virgola, seguita da un segno di sottrazione, seguito da una o più cifre decimali.|  
|`(\:\w{1,4}?)*`|Trovare la corrispondenza con zero o una occorrenza del segno di due punti, seguito dal numero minimo possibile di caratteri di spazio vuoto tra uno e quattro.|  
|`(?#case insensitive comparison)`|Un commento inline. Non ha effetto sul comportamento della corrispondenza tra modelli.|  
|`\}`|Trovare la corrispondenza con una parentesi graffa di chiusura.|  
|`(?x)`|Abilitare l'opzione per ignorare gli spazi vuoti nel modello in modo che il commento di fine riga venga riconosciuto.|  
|`# Looks for a composite format item.`|Un commento di fine riga.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 Si noti che, invece di fornire il `(?x)` costruire nell'espressione regolare, il commento potrebbe anche riconosciuto chiamando il <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> metodo e passando il <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> valore di enumerazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Linguaggio di espressioni regolari - Riferimento rapido](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
