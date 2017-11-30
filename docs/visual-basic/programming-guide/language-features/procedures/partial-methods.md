---
title: Metodi parziali (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ebedd6f8173e3c349240d24ddaf16e4841f67a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="partial-methods-visual-basic"></a>Metodi parziali (Visual Basic)
Metodi parziali consentono agli sviluppatori di inserire la logica personalizzata nel codice. In genere, il codice è parte di una classe generato da progettazione. Metodi parziali sono definiti in una classe parziale che viene creata da un generatore di codice e vengono utilizzati frequentemente per fornire la notifica che un elemento è stato modificato. Consentono allo sviluppatore di specificare un comportamento personalizzato in risposta alla modifica.  
  
 La finestra di progettazione del generatore di codice definisce solo la firma del metodo e uno o più chiamate al metodo. Gli sviluppatori possono quindi fornire le implementazioni del metodo, se si desidera personalizzare il comportamento del codice generato. Quando viene fornita alcuna implementazione, le chiamate al metodo vengono rimossi dal compilatore, risultante in nessun overhead di prestazioni.  
  
## <a name="declaration"></a>Dichiarazione  
 Il codice generato contrassegna la definizione di un metodo parziale inserendo la parola chiave `Partial` all'inizio della riga della firma.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 La definizione deve soddisfare le condizioni seguenti:  
  
-   Il metodo deve essere un `Sub`, non un `Function`.  
  
-   Il corpo del metodo deve essere lasciato vuoto.  
  
-   Il modificatore di accesso deve essere `Private`.  
  
## <a name="implementation"></a>Implementazione  
 L'implementazione è costituita principalmente nell'inserire il corpo del metodo parziale. L'implementazione è in genere in una classe parziale separata dalla definizione e viene scritto da uno sviluppatore che desidera estendere il codice generato.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 La firma nella dichiarazione consente di duplicare esattamente l'esempio precedente, ma sono possibili variazioni. In particolare, è possano aggiungere altri modificatori, ad esempio `Overloads` o `Overrides`. Un solo `Overrides` modificatore è consentito. Per ulteriori informazioni sui modificatori di metodo, vedere [istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Uso  
 Si chiama un metodo parziale procedendo come per qualsiasi altro `Sub` stored procedure. Se è stato implementato il metodo, gli argomenti vengono valutati e viene eseguito il corpo del metodo. Tuttavia, tenere presente che l'implementazione di un metodo parziale è facoltativa. Se non è stato implementato il metodo, una chiamata non ha alcun effetto e non vengono valutate le espressioni passate come argomenti al metodo.  
  
## <a name="example"></a>Esempio  
 In un file denominato Product.Designer.vb, definire un `Product` classe che ha un `Quantity` proprietà.  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 In un file denominato Product. vb, fornire un'implementazione per `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 Infine, nel metodo Main di un progetto, dichiarare un `Product` istanza e fornire un valore iniziale per il relativo `Quantity` proprietà.  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 Verrà visualizzata una finestra di messaggio che viene visualizzato questo messaggio:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Routine Sub](./sub-procedures.md)  
 [Parametri facoltativi](./optional-parameters.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Generazione di codice in LINQ to SQL](https://msdn.microsoft.com/library/bb399400)  
 [Aggiunta di logica di Business mediante metodi parziali](https://msdn.microsoft.com/library/bb546176)
