---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 0c855c4e08b365b4cb75ab062d2ec304a79612ab
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347909"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno del contesto di dichiarazione, incluso all'interno di qualsiasi tipo contenuto.  
  
## <a name="remarks"></a>Note  
 Se un elemento di programmazione rappresenta una funzionalità proprietaria o contiene dati riservati, in genere si vuole limitarne l'accesso al più possibile. Si ottiene la massima limitazione consentendo solo il modulo, la classe o la struttura che lo definisce per accedervi. Per limitare l'accesso a un elemento in questo modo, è possibile dichiararlo con `Private`.  

> [!NOTE]
> È anche possibile usare il modificatore di accesso [privato protetto](private-protected.md) , che rende accessibile un membro all'interno di tale classe e dalle classi derivate presenti nell'assembly contenitore.

## <a name="rules"></a>regole  

- **Contesto di dichiarazione.** Si può usare `Private` solo a livello di modulo. Ciò significa che il contesto di dichiarazione per un elemento di `Private` deve essere un modulo, una classe o una struttura e non può essere un file di origine, uno spazio dei nomi, un'interfaccia o una routine.  
  
## <a name="behavior"></a>Comportamento di  
  
- **Livello di accesso.** Tutto il codice all'interno di un contesto di dichiarazione può accedere ai relativi elementi `Private`. Incluso il codice all'interno di un tipo contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione. Nessun codice esterno al contesto di dichiarazione può accedere ai relativi elementi `Private`.  
  
- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*. Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Il modificatore `Private` può essere usato nei contesti seguenti:  
  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
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
- [Protected Friend](./protected-friend.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
