---
title: 'Procedura: Rimuovere caratteri non validi da una stringa'
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
- regular expressions, examples
- cleaning input
- user input, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f676ca9121498da7c88cdec8b49586bde91b181
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a>Procedura: Rimuovere caratteri non validi da una stringa
L'esempio seguente usa il metodo statico <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> metodo per rimuovere i caratteri non validi da una stringa.  
  
## <a name="example"></a>Esempio  
 È possibile usare il metodo `CleanInput` definito in questo esempio per rimuovere i caratteri potenzialmente dannosi che sono stati inseriti in un campo di testo che accetta l'input dell'utente. In questo caso, `CleanInput` rimuove tutti i caratteri non alfanumerici tranne punto (.), simboli "at" (@) e trattini (-) e restituisce la stringa restante. È tuttavia possibile modificare l'espressione regolare in modo che rimuova i caratteri che non devono essere inclusi in una stringa di input.  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 Il criterio di espressione regolare `[^\w\.@-]` corrisponde a qualsiasi carattere che non è un carattere alfanumerico, un punto, un simbolo @ o un trattino. Un carattere alfanumerico è qualsiasi lettera, numero decimale o connettore di punteggiatura, ad esempio un carattere di sottolineatura. Qualsiasi carattere che corrisponde a questo modello viene sostituito da <xref:System.String.Empty?displayProperty=nameWithType>, ovvero la stringa definita dal modello di sostituzione. Per consentire ulteriori caratteri nell'input dell'utente, aggiungere tali caratteri alla classe di caratteri nel criterio di espressione regolare. Ad esempio, il criterio di espressione regolare `[^\w\.@-\\%]` consente inoltre di un simbolo di percentuale e una barra rovesciata nella stringa di input.  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni regolari di .NET](../../../docs/standard/base-types/regular-expressions.md)
