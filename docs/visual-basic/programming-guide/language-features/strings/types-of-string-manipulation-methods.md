---
title: Tipi di metodi per la gestione delle stringhe in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b437be4a6f4a0cc9d5a4d21291a80c9cb8fffcd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Tipi di metodi per la gestione delle stringhe in Visual Basic
Esistono diversi modi per analizzare e modificare le stringhe. Alcuni dei metodi fanno parte di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language, mentre altri sono inerenti la `String` classe.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Linguaggio Visual Basic e .NET Framework  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]metodi vengono utilizzati come funzioni intrinseche del linguaggio. Essi possono essere utilizzati senza qualifica nel codice. Nell'esempio seguente viene illustrato un utilizzo tipico di un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] comando di modifica di stringhe:  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 In questo esempio, il `Mid` funzione esegue un'operazione diretta su `aString` e assegna il valore a `bString`.  
  
 Per un elenco di metodi di modifica stringa Visual Basic, vedere [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>I metodi condivisi e metodi di istanza  
 È inoltre possibile modificare le stringhe con i metodi del `String` classe. Esistono due tipi di metodi in `String`: *condivisa* metodi e *istanza* metodi.  
  
#### <a name="shared-methods"></a>Metodi condivisi  
 Un metodo condiviso è un metodo che deriva dalla `String` classe stessa e non richiede un'istanza di tale classe per funzionare. Questi metodi possono essere qualificati con il nome della classe (`String`) anziché con un'istanza di `String` classe. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 Nell'esempio precedente, il <xref:System.String.Copy%2A?displayProperty=nameWithType> è un metodo statico, che agisce su un'espressione fornita e assegna il valore risulta a `bString`.  
  
#### <a name="instance-methods"></a>Metodi di istanza  
 Metodi di istanza, invece, hanno origine da una particolare istanza di `String` e deve essere qualificato con il nome dell'istanza. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 In questo esempio, il <xref:System.String.Substring%2A?displayProperty=nameWithType> è un metodo di istanza di `String` (vale a dire `aString`). Esegue un'operazione su `aString` e assegna tale valore per `bString`.  
  
 Per ulteriori informazioni, vedere la documentazione per la <xref:System.String> classe.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
