---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 062d6276ab91705a4554da2afa8459a26453906f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703614"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati non sono restrizioni di accesso.  
  
## <a name="remarks"></a>Note  
 Se si sta pubblicando un componente o un set di componenti, ad esempio una libreria di classi, è consigliabile in genere gli elementi di programmazione sia accessibile da qualsiasi codice che interagisce con l'assembly. Per conferire tale accesso illimitato a un elemento, è possibile dichiararla con `Public`.  
  
 L'accesso pubblico è il livello normale per un elemento di programmazione quando non è necessario limitare l'accesso a esso. Si noti che il livello di accesso di un elemento dichiarato all'interno di un'interfaccia, modulo, classe o struttura per impostazione predefinita `Public` se non si dichiara in caso contrario.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** È possibile usare `Public` solo a livello di modulo, interfaccia o dello spazio dei nomi. Ciò significa che il contesto della dichiarazione per un `Public` elemento deve essere un file di origine, lo spazio dei nomi, interfaccia, modulo, classe o struttura e non può essere una procedura.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** Tutto il codice che può accedere a un modulo, classe o struttura può accedere ai relativi `Public` elementi.  
  
-   **Accesso predefinito.** Le variabili locali all'interno di una routine per impostazione predefinita per l'accesso pubblico ed è possono usare modificatori di accesso su di essi.  
  
-   **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*. Per un confronto tra i modificatori di accesso, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Il modificatore `Public` può essere usato nei contesti seguenti:  
  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
