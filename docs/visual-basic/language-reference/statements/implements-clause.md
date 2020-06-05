---
title: Clausola Implements
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
ms.openlocfilehash: 46ab1a1148e8d73d91293aedfc407e5efdc7cfb4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404563"
---
# <a name="implements-clause-visual-basic"></a>Clausola Implements (Visual Basic)
Indica che un membro di classe o di struttura fornisce l'implementazione per un membro definito in un'interfaccia.  
  
## <a name="remarks"></a>Commenti  
La `Implements` parola chiave non corrisponde all' [istruzione Implements](implements-statement.md). Usare l' `Implements` istruzione per specificare che una classe o una struttura implementa una o più interfacce, quindi per ogni membro si usa la `Implements` parola chiave per specificare l'interfaccia e il membro che implementa.

Se una classe o una struttura implementa un'interfaccia, deve includere l' `Implements` istruzione immediatamente dopo l'istruzione di [classe](class-statement.md) o di [struttura](structure-statement.md)e deve implementare tutti i membri definiti dall'interfaccia.

## <a name="reimplementation"></a>Reimplementazione  
In una classe derivata, è possibile reimplementare un membro di interfaccia che la classe base ha già implementato. Questa operazione è diversa rispetto all'override del membro della classe base nei seguenti aspetti:

- Non è necessario che il membro della classe base sia [sottoponibile a override](../modifiers/overridable.md) per essere reimplementato.
- È possibile reimplementare il membro con un nome diverso.

La `Implements` parola chiave può essere utilizzata nei contesti seguenti:

- [Istruzione Event](event-statement.md)
- [Istruzione Function](function-statement.md)
- [Property Statement](property-statement.md)
- [Istruzione Sub](sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](implements-statement.md)
- [Istruzione Interface](interface-statement.md)
- [Istruzione Class](class-statement.md)
- [Istruzione Structure](structure-statement.md)
