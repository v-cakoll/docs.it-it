---
title: Friend
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 4ac8e5942cf6097642ec111992ebfcdb91e8d7c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392171"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo all'interno dell'assembly che contiene la relativa dichiarazione.  
  
## <a name="remarks"></a>Commenti  
 In molti casi, si desidera che gli elementi di programmazione come classi e strutture siano utilizzati dall'intero assembly, non solo dal componente che li dichiara. Tuttavia, è possibile che non si desideri che siano accessibili dal codice all'esterno dell'assembly (ad esempio, se l'applicazione è proprietaria). Se si vuole limitare l'accesso a un elemento in questo modo, è possibile dichiararlo usando il `Friend` modificatore.  
  
 Il codice in altre classi, strutture e moduli compilati nello stesso assembly può accedere a tutti gli `Friend` elementi in tale assembly.  
  
 `Friend`l'accesso è spesso il livello preferenziale per gli elementi di programmazione di un'applicazione e `Friend` rappresenta il livello di accesso predefinito di un'interfaccia, un modulo, una classe o una struttura.  
  
 È possibile usare `Friend` solo a livello di modulo, interfaccia o spazio dei nomi. Il contesto di dichiarazione per un `Friend` elemento deve pertanto essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura e non può essere una routine.  

> [!NOTE]
> È anche possibile usare il modificatore di accesso [Friend protetto](protected-friend.md) , che rende accessibile un membro della classe da tale classe, dalle classi derivate e dallo stesso assembly in cui è definita la classe. Per limitare l'accesso a un membro dall'interno della relativa classe e dalle classi derivate nello stesso assembly, usare il modificatore di accesso [privato protetto](private-protected.md) .

 Per un confronto tra `Friend` e gli altri modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
> È possibile specificare che un altro assembly è un assembly Friend, che consente di accedere a tutti i tipi e membri contrassegnati come `Friend` . Per ulteriori informazioni, vedere [assembly Friend](../../../standard/assembly/friend.md).

## <a name="example"></a>Esempio  
 La classe seguente usa il `Friend` modificatore per consentire ad altri elementi di programmazione all'interno dello stesso assembly di accedere a determinati membri.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Uso  
 È possibile usare il `Friend` modificatore in questi contesti:  
  
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
  
 [Property Statement](../statements/property-statement.md)  
  
 [Istruzione Structure](../statements/structure-statement.md)  
  
 [Istruzione Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Pubblica](public.md)
- [Protetto](protected.md)
- [Privata](private.md)
- [Privato protetto](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
