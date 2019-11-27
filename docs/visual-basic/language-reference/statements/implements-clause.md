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
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345866"
---
# <a name="implements-clause-visual-basic"></a>Clausola Implements (Visual Basic)
Indica che un membro di classe o di struttura fornisce l'implementazione per un membro definito in un'interfaccia.  
  
## <a name="remarks"></a>Note  
La parola chiave `Implements` non corrisponde all' [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md). Usare l'istruzione `Implements` per specificare che una classe o una struttura implementa una o più interfacce, quindi per ogni membro si usa la parola chiave `Implements` per specificare l'interfaccia e il membro che implementa.

Se una classe o una struttura implementa un'interfaccia, deve includere l'istruzione `Implements` immediatamente dopo l'istruzione di [classe](../../../visual-basic/language-reference/statements/class-statement.md) o di [struttura](../../../visual-basic/language-reference/statements/structure-statement.md)e deve implementare tutti i membri definiti dall'interfaccia.

## <a name="reimplementation"></a>Reimplementazione  
In una classe derivata, è possibile reimplementare un membro di interfaccia che la classe base ha già implementato. Questa operazione è diversa rispetto all'override del membro della classe base nei seguenti aspetti:

- Non è necessario che il membro della classe base sia [sottoponibile a override](../../../visual-basic/language-reference/modifiers/overridable.md) per essere reimplementato.
- È possibile reimplementare il membro con un nome diverso.

La parola chiave `Implements` può essere utilizzata nei contesti seguenti:

- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
