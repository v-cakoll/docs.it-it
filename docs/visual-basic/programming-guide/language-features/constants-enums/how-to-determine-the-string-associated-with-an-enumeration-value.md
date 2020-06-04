---
title: 'Procedura: determinare la stringa associata a un valore di enumerazione'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 525da9206472afefa9f85b49ceee0775cbd168c3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414466"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>Procedura: determinare la stringa associata a un valore di enumerazione (Visual Basic)
I <xref:System.Enum.GetValues%2A> <xref:System.Enum.GetNames%2A> metodi e consentono di determinare le stringhe e i valori associati ai membri dell'enumerazione.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>Per determinare la stringa associata a un'enumerazione  
  
- Usare il <xref:System.Enum.GetNames%2A> metodo per recuperare le stringhe associate ai membri dell'enumerazione. Questo esempio dichiara un'enumerazione, `flavorEnum` , quindi usa il <xref:System.Enum.GetNames%2A> metodo per visualizzare le stringhe associate a ogni membro.  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [Procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Procedura: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md)
- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Procedura: scorrere un'enumerazione in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)
- [Istruzione Enum](../../../language-reference/statements/enum-statement.md)
