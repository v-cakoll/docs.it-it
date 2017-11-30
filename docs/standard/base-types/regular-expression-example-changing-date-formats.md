---
title: 'Esempio di espressione regolare: modifica dei formati di data'
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
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eeaed0951018c989612691065c027ee46bd6655a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-changing-date-formats"></a>Esempio di espressione regolare: modifica dei formati di data
Nell'esempio di codice viene illustrato come utilizzare il <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> metodo per sostituire le date che hanno il formato *mm*/*gg*/*yy* con le date il formato *gg*-*mm*-*aa*.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 Il codice seguente illustra come il metodo `MDYToDMY` può essere chiamato in un'applicazione.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a>Commenti  
 Criterio di espressione regolare `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` viene interpretato come illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`\b`|Inizia la corrispondenza sul confine di parola.|  
|`(?<month>\d{1,2})`|Trova la corrispondenza con una o due cifre decimali. Equivale al gruppo acquisito `month`.|  
|`/`|Corrisponde alla barra.|  
|`(?<day>\d{1,2})`|Trova la corrispondenza con una o due cifre decimali. Equivale al gruppo acquisito `day`.|  
|`/`|Corrisponde alla barra.|  
|`(?<year>\d{2,4})`|Corrisponde a due - quattro cifre decimali. Equivale al gruppo acquisito `year`.|  
|`\b`|Termina la corrispondenza sul confine di parola.|  
  
 Il modello `${day}-${month}-${year}` definisce la stringa di sostituzione come illustrato nella tabella seguente.  
  
|Criterio|Descrizione|  
|-------------|-----------------|  
|`$(day)`|Aggiunge la stringa acquisita dal gruppo di acquisizione `day`.|  
|`-`|Aggiunge un trattino.|  
|`$(month)`|Aggiunge la stringa acquisita dal gruppo di acquisizione `month`.|  
|`-`|Aggiunge un trattino.|  
|`$(year)`|Aggiunge la stringa acquisita dal gruppo di acquisizione `year`.|  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni regolari di .NET](../../../docs/standard/base-types/regular-expressions.md)
