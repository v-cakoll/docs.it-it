---
title: 'Procedura: determinare la stringa associata a un valore di enumerazione'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c396a4e2ebe973f5be65c3fab5f22cdedb29be1a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351139"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Procedura: determinare la stringa associata a un valore di enumerazione (Visual Basic)
I metodi <xref:System.Enum.GetValues%2A> e <xref:System.Enum.GetNames%2A> consentono di determinare le stringhe e i valori associati ai membri dell'enumerazione.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Per determinare la stringa associata a un'enumerazione  
  
- Usare il metodo <xref:System.Enum.GetNames%2A> per recuperare le stringhe associate ai membri dell'enumerazione. Questo esempio dichiara un'enumerazione, `flavorEnum`, quindi usa il metodo <xref:System.Enum.GetNames%2A> per visualizzare le stringhe associate a ogni membro.  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Quando usare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
