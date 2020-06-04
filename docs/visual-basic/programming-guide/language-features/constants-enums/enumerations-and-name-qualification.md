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
ms.openlocfilehash: 4b09284b8282c481e406050d37cbdb2f3c8686bc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414505"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Qualifica di nomi ed enumerazioni (Visual Basic)
In genere, quando si fa riferimento a un membro di un'enumerazione, è necessario qualificare il nome del membro con il nome dell'enumerazione. Per fare riferimento al `Sunday` membro dell'enumerazione, ad esempio `Days` , usare la sintassi seguente:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Utilizzo dell'istruzione Imports  
 È possibile evitare di usare nomi completi aggiungendo un' `Imports` istruzione alla sezione delle dichiarazioni dello spazio dei nomi del codice, come nell'esempio seguente:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 Un' `Imports` istruzione importa i nomi degli spazi dei nomi da progetti e assembly a cui viene fatto riferimento e dall'interno dello stesso progetto del modulo in cui viene visualizzata l'istruzione. Una volta aggiunta questa istruzione, è possibile fare riferimento ai membri dell'enumerazione senza qualifica, come nell'esempio seguente:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Organizzando set di costanti correlate nelle enumerazioni, è possibile utilizzare gli stessi nomi costanti in contesti diversi. Ad esempio, è possibile usare gli stessi nomi per le costanti dei giorni feriali `Days` nelle `WorkDays` enumerazioni e. Se si usa l' `Imports` istruzione con le enumerazioni, è necessario prestare attenzione per evitare riferimenti ambigui. Prendere in considerazione gli esempi seguenti:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Supponendo che `Monday` sia un membro dell' `Days` enumerazione e dell' `Workdays` enumerazione, questo codice genera un errore del compilatore. Per evitare riferimenti ambigui quando si fa riferimento a una singola costante, qualificare il nome della costante con la relativa enumerazione. Il codice seguente si riferisce alle `Saturday` costanti nelle `Days` `WorkDays` enumerazioni e.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>Vedere anche

- [Costanti ed enumerazioni](../../../language-reference/constants-and-enumerations.md)
- [Procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Procedura: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md)
- [Procedura: scorrere un'enumerazione in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Procedura: determinare la stringa associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)
- [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)
- [Istruzione Enum](../../../language-reference/statements/enum-statement.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Tipi di dati](../../../language-reference/data-types/index.md)
