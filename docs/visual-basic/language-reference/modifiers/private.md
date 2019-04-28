---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d6e28e5e87c3a88e4db3fc81177894683dbb0908
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920445"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dal contesto della dichiarazione, anche all'interno di qualsiasi tipo di contenuto.  
  
## <a name="remarks"></a>Note  
 Se un elemento di programmazione rappresenta funzionalità proprietarie o contiene dati riservati, in genere si desidera limitare l'accesso come rigorosamente possibili. Per ottenere il limite massimo di consentendo solo il modulo, classe o struttura che definisca in modo da accedervi. Per limitare l'accesso a un elemento in questo modo, è possibile dichiararla con `Private`.  

> [!NOTE]
> È anche possibile usare la [Private Protected](private-protected.md) modificatore di accesso, che rende accessibili da all'interno di tale classe e dalle classi derivate che si trova nel relativo assembly che contiene un membro.

## <a name="rules"></a>Regole  

- **Contesto della dichiarazione.** Si può usare `Private` solo a livello di modulo. Ciò significa che il contesto della dichiarazione per un `Private` elemento deve essere un modulo, classe o struttura e non può essere un file di origine, lo spazio dei nomi, interfaccia o procedura.  
  
## <a name="behavior"></a>Comportamento  
  
- **Livello di accesso.** Può accedere a tutto il codice all'interno di un contesto della dichiarazione relativo `Private` elementi. Ciò include il codice all'interno di un tipo di contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione. Non può accedere a nessun codice all'esterno del contesto di dichiarazione relativa `Private` elementi.  
  
- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*. Per un confronto tra i modificatori di accesso, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Il modificatore `Private` può essere usato nei contesti seguenti:  
  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
