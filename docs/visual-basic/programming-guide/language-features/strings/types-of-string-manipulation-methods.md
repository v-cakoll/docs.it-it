---
title: Tipi di metodi per la gestione delle stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: fa579303ad268a88269f360bdf626f9590c5d6a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648495"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Tipi di metodi per la gestione delle stringhe in Visual Basic
Esistono diversi modi per analizzare e modificare le stringhe. Alcuni metodi fanno parte del linguaggio Visual Basic e altri sono intrinseci di `String` classe.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Linguaggio Visual Basic e .NET Framework  
 Metodi di Visual Basic vengono utilizzati come funzioni intrinseche del linguaggio. Essi possono essere utilizzati senza qualifica nel codice. Nell'esempio seguente viene illustrato l'utilizzo tipico di un comando di modifica di stringhe Visual Basic:  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 In questo esempio, il `Mid` funzione esegue un'operazione diretta sugli `aString` e assegna il valore da `bString`.  
  
 Per un elenco di metodi di modifica di stringhe Visual Basic, vedere [riepilogo della modifica delle stringhe](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>I metodi condivisi e metodi di istanza  
 È inoltre possibile modificare le stringhe con i metodi del `String` classe. Esistono due tipi di metodi `String`: *condivisa* metodi e *istanza* metodi.  
  
#### <a name="shared-methods"></a>Metodi condivisi  
 Un metodo condiviso è un metodo che deriva dal `String` classe stessa e non richiede un'istanza di tale classe per funzionare. Questi metodi possono essere qualificati con il nome della classe (`String`) anziché con un'istanza del `String` classe. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 Nell'esempio precedente, il <xref:System.String.Copy%2A?displayProperty=nameWithType> è un metodo statico, che agisce su un'espressione fornita e assegna il valore risultante a `bString`.  
  
#### <a name="instance-methods"></a>Metodi di istanza  
 Metodi di istanza, invece, hanno origine da una particolare istanza di `String` e deve essere qualificato con il nome dell'istanza. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 In questo esempio, il <xref:System.String.Substring%2A?displayProperty=nameWithType> è un metodo dell'istanza di `String` (vale a dire `aString`). Esegue un'operazione sulla `aString` e assegna tale valore a `bString`.  
  
 Per altre informazioni, vedere la documentazione per il <xref:System.String> classe.  
  
## <a name="see-also"></a>Vedere anche
- [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
