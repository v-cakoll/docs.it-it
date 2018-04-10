---
title: Private (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dal contesto della dichiarazione, anche all'interno di qualsiasi tipo di contenuto.  
  
## <a name="remarks"></a>Note  
 Se un elemento di programmazione rappresenta una funzionalità proprietaria o contiene dati riservati, in genere si desidera limitare l'accesso come sia possibile. Per ottenere il limite massimo di consentire solo il modulo, classe o struttura che definisce per accedervi. Per limitare l'accesso a un elemento in questo modo, è possibile dichiarare con `Private`.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** Si può usare `Private` solo a livello di modulo. Ciò significa che il contesto della dichiarazione per un `Private` elemento deve essere un modulo, classe o struttura e non può essere un file di origine, lo spazio dei nomi, interfaccia o stored procedure.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** Può accedere a tutto il codice all'interno di un contesto della dichiarazione relativa `Private` elementi. Ciò include il codice all'interno di un tipo di contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione. Nessun codice all'esterno del contesto di dichiarazione può accedere il `Private` elementi.  
  
-   **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*. Per un confronto tra i modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
