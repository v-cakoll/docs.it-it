---
title: 'Procedura: Estrarre un protocollo e un numero di porta da un URL'
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
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Procedura: Estrarre un protocollo e un numero di porta da un URL
L'esempio seguente estrae un protocollo e un numero di porta da un URL.  
  
## <a name="example"></a>Esempio  
 Nell'esempio viene utilizzato il <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> per restituire il protocollo seguito da due punti seguiti dal numero di porta.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 Il modello di espressione regolare `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` può essere interpretato come indicato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`^`|Iniziare la ricerca della corrispondenza all'inizio della stringa.|  
|`(?<proto>\w+)`|Trova la corrispondenza di uno o più caratteri alfanumerici. Nome di questo gruppo `proto`.|  
|`://`|Trovare la corrispondenza di due punti seguiti da due barre.|  
|`[^/]+?`|Trovare la corrispondenza di una o più occorrenze (ma il minor numero possibile) di qualsiasi carattere diverso da una barra.|  
|`(?<port>:\d+)?`|Trovare la corrispondenza di zero o una occorrenza di due punti seguiti da una o più cifre. Nome di questo gruppo `port`.|  
|`/`|Trovare la corrispondenza di una barra.|  
  
 Il <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> metodo espande la `${proto}${port}` sequenza di sostituzione che concatena il valore di due gruppi denominati acquisiti nel modello di espressione regolare. È una valida alternativa in modo esplicito della concatenazione delle stringhe recuperate dall'oggetto della raccolta restituita dal <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> proprietà.  
  
 Nell'esempio viene utilizzato il <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> metodo con due sostituzioni, `${proto}` e `${port}`, per includere i gruppi acquisiti nella stringa di output. È possibile recuperare i gruppi acquisiti della corrispondenza <xref:System.Text.RegularExpressions.GroupCollection> invece, come illustrato nel codice seguente.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni regolari di .NET](../../../docs/standard/base-types/regular-expressions.md)
