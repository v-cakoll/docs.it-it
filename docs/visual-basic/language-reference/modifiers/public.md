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
ms.openlocfilehash: 35332e50227cdef6386362df17c10b5b2cdaa689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415349"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati non hanno restrizioni di accesso.  
  
## <a name="remarks"></a>Commenti  
 Se si pubblica un componente o un set di componenti, ad esempio una libreria di classi, in genere si vuole che gli elementi di programmazione siano accessibili da qualsiasi codice che interagisce con l'assembly. Per conferire l'accesso illimitato a un elemento, è possibile dichiararlo con `Public` .  
  
 L'accesso pubblico è il livello normale per un elemento di programmazione quando non è necessario limitarne l'accesso. Si noti che il livello di accesso di un elemento dichiarato all'interno di un'interfaccia, di un modulo, di una classe o di una struttura viene impostato sul valore predefinito `Public` se non viene dichiarato in caso contrario.  
  
## <a name="rules"></a>Regole  
  
- **Contesto della dichiarazione. ** È possibile usare `Public` solo a livello di modulo, interfaccia o spazio dei nomi. Ciò significa che il contesto di dichiarazione per un `Public` elemento deve essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura e non può essere una routine.  
  
## <a name="behavior"></a>Comportamento  
  
- **Livello di accesso.** Tutto il codice che può accedere a un modulo, una classe o una struttura può accedere ai relativi `Public` elementi.  
  
- **Accesso predefinito.** Per impostazione predefinita, le variabili locali all'interno di una stored procedure non possono usare alcun modificatore di accesso.  
  
- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*. Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 Il modificatore `Public` può essere usato nei contesti seguenti:  
  
 [Istruzione Class](../statements/class-statement.md)  
  
 [Istruzione Const](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Istruzione Delegate](../statements/delegate-statement.md)  
  
 [Istruzione Dim](../statements/dim-statement.md)  
  
 [Istruzione Enum](../statements/enum-statement.md)  
  
 [Istruzione Event](../statements/event-statement.md)  
  
 [Istruzione Function](../statements/function-statement.md)  
  
 [Istruzione Interface](../statements/interface-statement.md)  
  
 [Istruzione Module](../statements/module-statement.md)  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Istruzione Structure](../statements/structure-statement.md)  
  
 [Istruzione Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Protetto](protected.md)
- [Amico](friend.md)
- [Privata](private.md)
- [Privato protetto](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
