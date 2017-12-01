---
title: Costrutti di backreference nelle espressioni regolari
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
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a884e70f542c2ed7ff63e39cb7eadedf0ef7b4d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a>Costrutti di backreference nelle espressioni regolari
I backreference sono uno strumento utile per identificare un carattere ripetuto o una sottostringa all'interno di una stringa. Se la stringa di input contiene ad esempio più occorrenze di una sottostringa arbitraria, è possibile trovare la prima occorrenza con un gruppo di acquisizione e usare un backreference per trovare le occorrenze successive della sottostringa.  
  
> [!NOTE]
>  Per fare riferimento a gruppi di acquisizione denominati e numerati in stringhe sostitutive, si usa una sintassi separata. Per altre informazioni, vedere [Substitutions](substitutions-in-regular-expressions.md).  
  
 .NET definisce elementi di linguaggio separati per fare riferimento a gruppi di acquisizione denominati e numerati. Per ulteriori informazioni sui gruppi di acquisizione, vedere [costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
## <a name="numbered-backreferences"></a>Backreference numerati  
 Nei backreference numerati si usa la sintassi seguente:  
  
 `\` *numero*  
  
 dove *numero* è la posizione corretta del gruppo di acquisizione nell'espressione regolare. Ad esempio, `\4` corrisponde al contenuto del quarto gruppo di acquisizione. Se *numero* non definito nel criterio di espressione regolare, si verifica un errore di analisi e il motore delle espressioni regolari genera un <xref:System.ArgumentException>. Ad esempio, l'espressione regolare `\b(\w+)\s\1` è valida, poiché `(\w+)` è il primo e l'unico gruppo di acquisizione nell'espressione. D'altra parte, `\b(\w+)\s\2` non è un'espressione valida e genera un'eccezione di argomento, perché non esistono gruppi di acquisizione numerati `\2`.  
  
 Si noti l'ambiguità tra i codici di escape ottale (ad esempio `\16`) e `\` *numero* backreference che usano la stessa notazione. Questa ambiguità viene risolta nel modo seguente:  
  
-   Le espressioni da `\1` a `\9` vengono sempre interpretate come backreference e non come codici ottali.  
  
-   Se la prima cifra di un'espressione composta da più cifre è 8 o 9, ad esempio `\80` o `\91`, l'espressione viene interpretata come valore letterale.  
  
-   Le espressioni con numerazione a partire da `\10` vengono considerate backreference se esiste un backreference a tale numero; in caso contrario, vengono interpretate come codici ottali.  
  
-   Se un'espressione regolare contiene un backreference in un numero di gruppo indefinito, si verifica un errore di analisi e il motore delle espressioni regolari genera un <xref:System.ArgumentException>.  
  
 Se l'ambiguità costituisce un problema, è possibile utilizzare il `\k<` *nome* `>` notazione, che è ambiguo e non può essere confuso con ottali. Analogamente, i codici esadecimale come `\xdd` non sono ambigui e non possono essere confusi con backreference.  
  
 L'esempio seguente consente di trovare caratteri alfanumerici doppi all'interno di una stringa. Viene definita un'espressione regolare `(\w)\1` costituita dagli elementi seguenti.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`(\w)`|Trova la corrispondenza di un carattere alfanumerico e la assegna al primo gruppo di acquisizione.|  
|`\1`|Trova la corrispondenza del carattere successivo, uguale al valore del primo gruppo di acquisizione.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a>Backreference denominati  
 Per definire un backreference denominato, usare la sintassi seguente:  
  
 `\k<` *nome* `>`  
  
 oppure:  
  
 `\k'` *name* `'`  
  
 dove *nome* è il nome di un gruppo di acquisizione definito nel modello di espressione regolare. Se *nome* non definito nel criterio di espressione regolare, si verifica un errore di analisi e il motore delle espressioni regolari genera un <xref:System.ArgumentException>.  
  
 L'esempio seguente consente di trovare caratteri alfanumerici doppi all'interno di una stringa. Viene definita un'espressione regolare `(?<char>\w)\k<char>` costituita dagli elementi seguenti.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`(?<char>\w)`|Corrisponde a un carattere alfanumerico e assegnarlo a un gruppo di acquisizione denominato `char`.|  
|`\k<char>`|Corrisponde al carattere successivo è lo stesso valore di `char` gruppo di acquisizione.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 Si noti che *nome* può anche essere la rappresentazione di stringa di un numero. Nell'esempio seguente viene usata l'espressione regolare `(?<2>\w)\k<2>` per trovare caratteri alfanumerici doppi all'interno di una stringa.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a>Corrispondenza dei backreference  
 Un backreference fa riferimento alla definizione più recente di un gruppo, vale a dire alla definizione all'estrema sinistra, in caso di corrispondenza da sinistra a destra. Quando un gruppo esegue più acquisizioni, un backreference fa riferimento all'acquisizione più recente.  
  
 L'esempio seguente include un modello di espressione regolare `(?<1>a)(?<1>\1b)*`, che ridefinisce il gruppo denominato \1. Nella tabella seguente sono descritti i modelli di espressione regolare.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`(?<1>a)`|Corrispondenza con il carattere "a" e assegnare il risultato al gruppo di acquisizione denominato `1`.|  
|`(?<1>\1b)*`|Occorrenza di corrispondenza di 0 o 1 del gruppo denominato `1` insieme a un "b" e di assegnare il risultato al gruppo di acquisizione denominato `1`.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 Confrontando l'espressione regolare con la stringa di input ("aababb"), il motore delle espressioni regolari esegue le operazioni seguenti:  
  
1.  Parte dall'inizio della stringa e trova una corrispondenza per "a" con l'espressione `(?<1>a)`. Il valore di `1` gruppo è ora "a".  
  
2.  Passa al secondo carattere e trova una corrispondenza per la stringa "ab" con l'espressione `\1b` o "ab". Assegna il risultato "ab" a `\1`.  
  
3.  Passa al quarto carattere. Per l'espressione `(?<1>\1b)` la corrispondenza individuata deve essere zero o più volte, ai fini di una corrispondenza corretta della stringa "abb" con l'espressione `\1b`. Assegna il risultato "abb" nuovamente a `\1`.  
  
 In questo esempio `*` è un quantificatore di cicli, vale a dire che viene eseguito ripetutamente finché il motore delle espressioni regolari non trova una corrispondenza con il modello che definisce. I quantificatori di cicli non cancellano le definizioni di gruppi.  
  
 Se un gruppo non ha acquisito alcuna sottostringa, un backreference a tale gruppo risulterà non definito e non troverà mai corrispondenza. Questo comportamento è illustrato il modello di espressione regolare `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, che viene definito come segue:  
  
|Criterio|Descrizione|  
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
 [Linguaggio di espressioni regolari - Riferimento rapido](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
