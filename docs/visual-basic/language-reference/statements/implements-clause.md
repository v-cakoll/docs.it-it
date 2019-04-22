---
title: Clausola Implements (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 05de1d9f8966c17d84deba34f27819cce4aff3fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832619"
---
# <a name="implements-clause-visual-basic"></a>Clausola Implements (Visual Basic)
Indica che un membro di classe o struttura fornisce l'implementazione per un membro definito in un'interfaccia.  
  
## <a name="remarks"></a>Note  
Il `Implements` parola chiave non è quello utilizzato per il [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md). Si utilizza il `Implements` istruzione per specificare che una classe o struttura implementa una o più interfacce, e quindi per ogni membro è usare il `Implements` parola chiave per specificare quale interfaccia e il membro implementa.

Se una classe o struttura implementa un'interfaccia, deve includere il `Implements` istruzione immediatamente dopo il [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md) oppure [Structure-istruzione](../../../visual-basic/language-reference/statements/structure-statement.md), e deve implementare tutti i membri definiti dall'interfaccia.

## <a name="reimplementation"></a>Reimplementazione  
In una classe derivata, si può reimplementare un membro di interfaccia che ha già implementato la classe di base. Questo comportamento è diverso dall'override del membro della classe base per i seguenti aspetti:

- Il membro della classe base non dovrà essere [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) per essere reimplementata.
- Si può reimplementare il membro con un nome diverso.

Il `Implements` parola chiave può essere utilizzata nei contesti seguenti:
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
