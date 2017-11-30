---
title: Qualifica di nomi ed enumerazioni (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb97d6a8f4b7e81f2b759010214e200ec63ff21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Qualifica di nomi ed enumerazioni (Visual Basic)
In genere, quando si fa riferimento a un membro di enumerazione, è necessario qualificare il nome del membro con il nome dell'enumerazione. Ad esempio, per fare riferimento al `Sunday` appartenente il `Days` enumerazione, è necessario utilizzare la sintassi seguente:  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a>Utilizzo dell'istruzione Imports  
 È possibile evitare l'utilizzo dei nomi completi aggiungendo un `Imports` istruzione alla sezione delle dichiarazioni dello spazio dei nomi del codice, come nell'esempio seguente:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 Un `Imports` istruzione Importa spazi dei nomi da progetti di riferimento e assembly e dall'interno dello stesso progetto del modulo in cui verrà visualizzata l'istruzione. Una volta aggiunta questa istruzione, è possibile fare riferimento ai membri dell'enumerazione senza qualifica, come nell'esempio seguente:  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 L'organizzazione di set di costanti correlate nelle enumerazioni, è possibile utilizzare gli stessi nomi di costanti in contesti diversi. Ad esempio, è possibile utilizzare gli stessi nomi per le costanti del giorno della settimana di `Days` e `WorkDays` enumerazioni. Se si utilizza il `Imports` istruzione con le enumerazioni, è necessario prestare attenzione a evitare riferimenti ambigui. Si consideri l'esempio seguente:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 Supponendo che `Monday` è un membro di entrambi i `Days` enumerazione e `Workdays` enumerazione, questo codice genera un errore del compilatore. Per evitare riferimenti ambigui quando si fa riferimento a una singola costante, qualificare il nome della costante con il tipo di enumerazione. Il codice seguente fa riferimento al `Saturday` le costanti di `Days` e `WorkDays` enumerazioni.  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Quando usare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
