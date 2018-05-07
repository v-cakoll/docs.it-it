---
title: 'Procedura: creare stringhe utilizzando StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 49f3271d41e9e858c6ecafe1dde5330ebff767f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Procedura: creare stringhe utilizzando StringBuilder in Visual Basic
In questo esempio viene costruita una stringa lunga da molte stringhe più piccole utilizzando la <xref:System.Text.StringBuilder> classe. Il <xref:System.Text.StringBuilder> classe risulta più efficiente il `&=` operatore per concatenare più stringhe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente crea un'istanza di <xref:System.Text.StringBuilder> classe aggiunte 1.000 stringhe a tale istanza e quindi restituisce la rappresentazione di stringa.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Uso della classe StringBuilder](../../../../standard/base-types/stringbuilder.md)  
 [Operatore &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Creazione di nuove stringhe](../../../../standard/base-types/creating-new.md)  
 [Modifica di stringhe](../../../../standard/base-types/manipulating-strings.md)  
 [Esempio di stringhe](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))
