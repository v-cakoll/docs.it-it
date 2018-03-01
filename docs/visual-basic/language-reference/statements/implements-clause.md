---
title: Clausola Implements (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73f66eda29e37fda15b4c838da5a0458684131da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implements-clause-visual-basic"></a>Clausola Implements (Visual Basic)
Indica che un membro di classe o struttura fornisce l'implementazione per un membro definito in un'interfaccia.  
  
## <a name="remarks"></a>Note  
Il `Implements` (parola chiave) non corrisponde la [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md). Utilizzare il `Implements` istruzione per specificare che una classe o struttura implementa una o più interfacce, e quindi per ogni membro il `Implements` (parola chiave) per specificare l'interfaccia e il membro implementa.

Se una classe o struttura implementa un'interfaccia, è necessario includere il `Implements` istruzione immediatamente dopo il [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md) o [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md), e deve implementare tutti i membri definito dall'interfaccia.

## <a name="reimplementation"></a>Nuove implementazione  
In una classe derivata, si può reimplementare un membro di interfaccia che la classe di base ha già implementato. Questo comportamento è diverso da cui si esegue l'override del membro della classe base per i seguenti aspetti:

- Il membro della classe base non è necessario essere [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) per essere reimplementato.
- È possibile reimplementare il membro con un nome diverso.

Il `Implements` parola chiave può essere utilizzata nei contesti seguenti:
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
