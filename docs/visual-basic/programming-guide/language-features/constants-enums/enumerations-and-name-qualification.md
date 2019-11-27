---
title: Qualifica di nomi ed enumerazioni
ms.date: 07/20/2015
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
ms.openlocfilehash: 4121266447b771ba954ad52a46e0d8b88de3f9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347492"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Qualifica di nomi ed enumerazioni (Visual Basic)
In genere, quando si fa riferimento a un membro di un'enumerazione, è necessario qualificare il nome del membro con il nome dell'enumerazione. Ad esempio, per fare riferimento al membro `Sunday` dell'enumerazione `Days`, usare la sintassi seguente:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Utilizzo dell'istruzione Imports  
 È possibile evitare l'uso di nomi completi aggiungendo un'istruzione `Imports` alla sezione delle dichiarazioni dello spazio dei nomi del codice, come nell'esempio seguente:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 Un'istruzione `Imports` importa i nomi degli spazi dei nomi da progetti e assembly a cui viene fatto riferimento e dall'interno dello stesso progetto del modulo in cui viene visualizzata l'istruzione. Una volta aggiunta questa istruzione, è possibile fare riferimento ai membri dell'enumerazione senza qualifica, come nell'esempio seguente:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Organizzando set di costanti correlate nelle enumerazioni, è possibile utilizzare gli stessi nomi costanti in contesti diversi. Ad esempio, è possibile usare gli stessi nomi per le costanti dei giorni feriali nelle enumerazioni `Days` e `WorkDays`. Se si usa l'istruzione `Imports` con le enumerazioni, è necessario prestare attenzione a evitare riferimenti ambigui. Si consideri l'esempio seguente:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Supponendo che `Monday` sia un membro dell'enumerazione `Days` e dell'enumerazione `Workdays`, questo codice genera un errore del compilatore. Per evitare riferimenti ambigui quando si fa riferimento a una singola costante, qualificare il nome della costante con la relativa enumerazione. Il codice seguente si riferisce alle costanti `Saturday` nelle enumerazioni `Days` e `WorkDays`.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>Vedere anche

- [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Procedura: Fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Procedura: Determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Quando usare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
