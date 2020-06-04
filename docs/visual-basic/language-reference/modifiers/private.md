---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 524f03e77e075bef08a1b41b563985de41baacb6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404810"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno del contesto di dichiarazione, incluso all'interno di qualsiasi tipo contenuto.  
  
## <a name="remarks"></a>Commenti  
 Se un elemento di programmazione rappresenta una funzionalità proprietaria o contiene dati riservati, in genere si vuole limitarne l'accesso al più possibile. Si ottiene la massima limitazione consentendo solo il modulo, la classe o la struttura che lo definisce per accedervi. Per limitare l'accesso a un elemento in questo modo, è possibile dichiararlo con `Private` .  

> [!NOTE]
> È anche possibile usare il modificatore di accesso [privato protetto](private-protected.md) , che rende accessibile un membro all'interno di tale classe e dalle classi derivate presenti nell'assembly contenitore.

## <a name="rules"></a>Regole  

- **Contesto della dichiarazione. ** Si può usare `Private` solo a livello di modulo. Ciò significa che il contesto di dichiarazione per un `Private` elemento deve essere un modulo, una classe o una struttura e non può essere un file di origine, uno spazio dei nomi, un'interfaccia o una routine.  
  
## <a name="behavior"></a>Comportamento  
  
- **Livello di accesso.** Tutto il codice all'interno di un contesto di dichiarazione può accedere ai relativi `Private` elementi. Incluso il codice all'interno di un tipo contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione. Nessun codice esterno al contesto di dichiarazione può accedere ai relativi `Private` elementi.  
  
- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*. Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 Il modificatore `Private` può essere usato nei contesti seguenti:  
  
 [Istruzione Class](../statements/class-statement.md)  
  
 [Istruzione Const](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Istruzione Delegate](../statements/delegate-statement.md)  
  
 [Istruzione Dim](../statements/dim-statement.md)  
  
 [Istruzione Enum](../statements/enum-statement.md)  
  
 [Istruzione Event](../statements/event-statement.md)  
  
 [Istruzione Function](../statements/function-statement.md)  
  
 [Istruzione Interface](../statements/interface-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Istruzione Structure](../statements/structure-statement.md)  
  
 [Istruzione Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Pubblica](public.md)
- [Protetto](protected.md)
- [Amico](friend.md)
- [Privato protetto](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
