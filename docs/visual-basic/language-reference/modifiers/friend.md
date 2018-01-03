---
title: Friend (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df0e8ad1990fe7a1aa495e1794c942813cffb5bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno dell'assembly che contiene la dichiarazione.  
  
## <a name="remarks"></a>Note  
 In molti casi, si desidera elementi, ad esempio le classi e da usare con l'intero assembly, non solo tramite il componente che li dichiara delle strutture di programmazione. Tuttavia, potrebbe non desiderati siano accessibili dal codice all'esterno dell'assembly (ad esempio, se l'applicazione è proprietario). Se si desidera limitare l'accesso a un elemento in questo modo, è possibile dichiarare utilizzando il `Friend` modificatore.  
  
 Codice in altre classi, strutture e i moduli compilati nello stesso assembly possono accedere a tutti i `Friend` elementi in tale assembly.  
  
 `Friend`l'accesso è spesso il livello preferito per gli elementi di programmazione dell'applicazione, e `Friend` è l'accesso predefinito di un'interfaccia, un modulo, una classe o una struttura.  
  
 È possibile utilizzare `Friend` solo a livello di modulo, interfaccia o spazio dei nomi. Pertanto, il contesto della dichiarazione per un `Friend` elemento deve essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura, non può essere una stored procedure.  
  
 È possibile utilizzare il `Friend` modificatore in combinazione con il [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modificatore nella stessa dichiarazione. Questa combinazione conferisce entrambi `Friend` accesso e l'accesso protetto per gli elementi dichiarati, in modo che siano accessibili da un punto qualsiasi nello stesso assembly, dalla rispettiva classe e dalle classi derivate. È possibile specificare `Protected Friend` solo in membri di classi.  
  
 Per un confronto tra `Friend` e l'altro modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  È possibile specificare che un altro assembly sia un assembly friend, che consente di accedere a tutti i tipi e membri contrassegnati come `Friend`. Per altre informazioni, vedere [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md) (Assembly friend).  
  
## <a name="example"></a>Esempio  
 La classe seguente usa il `Friend` modificatore per consentire altri elementi di programmazione all'interno dell'assembly stesso per accedere a determinati membri.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a>Utilizzo  
 È possibile utilizzare il `Friend` modificatore nei contesti seguenti:  
  
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
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
