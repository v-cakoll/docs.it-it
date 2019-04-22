---
title: 'Procedura: Creare stringhe usando StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834192"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Procedura: Creare stringhe usando StringBuilder in Visual Basic
Questo esempio si costruisce una stringa lunga da molte stringhe più piccole mediante il <xref:System.Text.StringBuilder> classe. Il <xref:System.Text.StringBuilder> classe risulta più efficiente il `&=` operatore per concatenano più stringhe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un'istanza di <xref:System.Text.StringBuilder> (classe), aggiunge le stringhe di 1.000 a tale istanza e quindi restituisce una rappresentazione di stringa.  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a>Vedere anche

- [Uso della classe StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [Operatore &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Creazione di nuove stringhe](../../../../standard/base-types/creating-new.md)
- [Modifica di stringhe](../../../../standard/base-types/manipulating-strings.md)
