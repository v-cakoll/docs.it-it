---
title: Pubblico
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351287"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati non hanno restrizioni di accesso.  
  
## <a name="remarks"></a>Osservazioni  
 Se si pubblica un componente o un set di componenti, ad esempio una libreria di classi, in genere si vuole che gli elementi di programmazione siano accessibili da qualsiasi codice che interagisce con l'assembly. Per conferire l'accesso illimitato a un elemento, è possibile dichiararlo con `Public`.  
  
 L'accesso pubblico è il livello normale per un elemento di programmazione quando non è necessario limitarne l'accesso. Si noti che il livello di accesso di un elemento dichiarato all'interno di un'interfaccia, di un modulo, di una classe o di una struttura viene impostato su `Public` se non viene dichiarato in caso contrario.  
  
## <a name="rules"></a>Regole  
  
- **Contesto di dichiarazione.** È possibile usare `Public` solo a livello di modulo, interfaccia o spazio dei nomi. Ciò significa che il contesto di dichiarazione per un elemento di `Public` deve essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura e non può essere una routine.  
  
## <a name="behavior"></a>Comportamento  
  
- **Livello di accesso.** Tutto il codice che può accedere a un modulo, una classe o una struttura può accedere ai relativi elementi `Public`.  
  
- **Accesso predefinito.** Per impostazione predefinita, le variabili locali all'interno di una stored procedure non possono usare alcun modificatore di accesso.  
  
- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*. Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
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
