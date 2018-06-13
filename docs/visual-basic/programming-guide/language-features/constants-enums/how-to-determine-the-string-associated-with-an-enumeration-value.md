---
title: 'Procedura: determinare la stringa associata a un valore di enumerazione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c14ea61feba7d7d85f9a4fc377aefdd8fa240c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651700"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Procedura: determinare la stringa associata a un valore di enumerazione (Visual Basic)
Il <xref:System.Enum.GetValues%2A> e <xref:System.Enum.GetNames%2A> metodi consentono di determinare le stringhe e valori associati ai membri di enumerazione.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Per determinare la stringa associata a un'enumerazione  
  
-   Utilizzare il <xref:System.Enum.GetNames%2A> metodo per recuperare le stringhe associate ai membri di enumerazione. In questo esempio dichiara un'enumerazione, `flavorEnum`, quindi viene utilizzato il <xref:System.Enum.GetNames%2A> metodo per visualizzare le stringhe associate a ogni membro.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Enum.GetValues%2A>  
 <xref:System.Enum.GetNames%2A>  
 <xref:System.Enum>  
 [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Quando usare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
