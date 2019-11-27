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
ms.openlocfilehash: 98f8ed947c9f4376c5778011a3a91ca8b094f9ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351570"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo all'interno dell'assembly che contiene la relativa dichiarazione.  
  
## <a name="remarks"></a>Osservazioni  
 In molti casi, si desidera che gli elementi di programmazione come classi e strutture siano utilizzati dall'intero assembly, non solo dal componente che li dichiara. Tuttavia, è possibile che non si desideri che siano accessibili dal codice all'esterno dell'assembly (ad esempio, se l'applicazione è proprietaria). Se si desidera limitare l'accesso a un elemento in questo modo, è possibile dichiararlo utilizzando il modificatore `Friend`.  
  
 Il codice in altre classi, strutture e moduli compilati nello stesso assembly può accedere a tutti gli elementi `Friend` in tale assembly.  
  
 `Friend` Access è spesso il livello preferenziale per gli elementi di programmazione di un'applicazione e `Friend` è il livello di accesso predefinito di un'interfaccia, un modulo, una classe o una struttura.  
  
 È possibile usare `Friend` solo a livello di modulo, interfaccia o spazio dei nomi. Pertanto, il contesto di dichiarazione per un elemento di `Friend` deve essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura; non può essere una procedura.  

> [!NOTE]
> È anche possibile usare il modificatore di accesso [Friend protetto](protected-friend.md) , che rende accessibile un membro della classe da tale classe, dalle classi derivate e dallo stesso assembly in cui è definita la classe. Per limitare l'accesso a un membro dall'interno della relativa classe e dalle classi derivate nello stesso assembly, usare il modificatore di accesso [privato protetto](private-protected.md) .

 Per un confronto tra `Friend` e gli altri modificatori di accesso, vedere [livelli di accesso nel Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
> È possibile specificare che un altro assembly è un assembly Friend, che consente di accedere a tutti i tipi e i membri contrassegnati come `Friend`. Per altre informazioni, vedere [Friend Assemblies](../../../standard/assembly/friend.md) (Assembly friend).

## <a name="example"></a>Esempio  
 La classe seguente usa il modificatore `Friend` per consentire ad altri elementi di programmazione all'interno dello stesso assembly di accedere a determinati membri.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Utilizzo  
 È possibile usare il modificatore `Friend` in questi contesti:  
  
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
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
