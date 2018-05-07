---
title: Protected (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 3866e7dd72b9e7145cf76f480bb5ffc6239a775e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno della propria classe o da una classe derivata.  
  
## <a name="remarks"></a>Note  
 Talvolta un elemento di programmazione dichiarato in una classe contiene dati sensibili o codice con restrizioni, e si desidera limitare l'accesso all'elemento. Tuttavia, se la classe è ereditabile e si prevede una gerarchia di classi derivate, potrebbe essere necessario per queste classi derivate di accedere ai dati o codice. In tal caso, si desidera l'elemento deve essere accessibile dalla classe di base e da tutte le classi derivate. Per limitare l'accesso a un elemento in questo modo, è possibile dichiarare con `Protected`.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** È possibile utilizzare `Protected` solo a livello di classe. Ciò significa che il contesto della dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o stored procedure.  
  
-   **Modificatori combinati.** È possibile utilizzare il `Protected` modificatore insieme con il [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modificatore nella stessa dichiarazione. Questa combinazione rende gli elementi dichiarati accessibili da un punto qualsiasi nello stesso assembly, dalla rispettiva classe e dalle classi derivate. È possibile specificare `Protected Friend` solo in membri di classi.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** Tutto il codice in una classe possa accedere ai relativi elementi. Codice di qualsiasi classe che deriva da una classe di base può accedere a tutti i `Protected` gli elementi della classe di base. Questo vale per tutte le generazioni di derivazione. Ciò significa che possa accedere a una classe `Protected` gli elementi della classe di base della classe base e così via.  
  
     Accesso protetto non è un superset o un sottoinsieme di accesso friend.  
  
-   **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*. Per un confronto tra i modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Il modificatore `Protected` può essere usato nei contesti seguenti:  
  
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
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
