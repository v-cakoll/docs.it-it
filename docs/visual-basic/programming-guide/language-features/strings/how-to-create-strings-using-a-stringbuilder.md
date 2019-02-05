---
title: 'Procedura: Creare stringhe usando StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: dec1afdbd3ca6c0ba719a95906de8cf6fc7ba378
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738799"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Procedura: Creare stringhe usando StringBuilder in Visual Basic
Questo esempio si costruisce una stringa lunga da molte stringhe più piccole mediante il <xref:System.Text.StringBuilder> classe. Il <xref:System.Text.StringBuilder> classe risulta più efficiente il `&=` operatore per concatenano più stringhe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un'istanza di <xref:System.Text.StringBuilder> (classe), aggiunge le stringhe di 1.000 a tale istanza e quindi restituisce una rappresentazione di stringa.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Uso della classe StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [Operatore &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Creazione di nuove stringhe](../../../../standard/base-types/creating-new.md)
- [Modifica di stringhe](../../../../standard/base-types/manipulating-strings.md)
