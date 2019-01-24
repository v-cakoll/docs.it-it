---
title: Metodi parziali (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: a974a68010fe80a07e83ac31e109bbf1c2b955e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568777"
---
# <a name="partial-methods-visual-basic"></a>Metodi parziali (Visual Basic)
I metodi parziali consentono agli sviluppatori di inserire la logica personalizzata nel codice. In genere, il codice è parte di una classe generato da progettazione. I metodi parziali sono definiti in una classe parziale che viene creata da un generatore di codice e vengono utilizzati frequentemente alla invierà una notifica che un elemento è stato modificato. Consentono allo sviluppatore di specificare un comportamento personalizzato in risposta alla modifica.  
  
 La finestra di progettazione del generatore di codice definisce solo la firma del metodo e uno o più chiamate al metodo. Gli sviluppatori possono quindi fornire le implementazioni del metodo se desiderano personalizzare il comportamento del codice generato. Quando non viene fornita alcuna implementazione, le chiamate al metodo vengono rimosse dal compilatore, risultante in nessun overhead aggiuntivi relativi alle prestazioni.  
  
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
 L'implementazione consiste principalmente nell'inserire il corpo del metodo parziale. L'implementazione è in genere in una classe parziale separata dalla definizione e viene scritto da uno sviluppatore che desidera estendere il codice generato.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 La firma nella dichiarazione consente di duplicare esattamente l'esempio precedente, ma sono possibili variazioni. In particolare, è possano aggiungere altri modificatori, ad esempio `Overloads` o `Overrides`. Un solo `Overrides` modificatore è consentito. Per altre informazioni sui modificatori di metodo, vedere [istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Usa  
 Si chiama un metodo parziale procedendo come per qualsiasi altro `Sub` procedure. Se è stato implementato il metodo, gli argomenti vengono valutati e il corpo del metodo viene eseguito. Tuttavia, tenere presente che l'implementazione di un metodo parziale è facoltativo. Se il metodo non è implementato, una chiamata non ha alcun effetto e non vengono valutate le espressioni passate come argomenti al metodo.  
  
## <a name="example"></a>Esempio  
 In un file denominato Product.Designer.vb, definire un `Product` classe avente un `Quantity` proprietà.  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 In un file denominato Product. vb, fornire un'implementazione per `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 Infine, nel metodo principale di un progetto, dichiarare un `Product` dell'istanza e fornire un valore iniziale per relativo `Quantity` proprietà.  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 Verrà visualizzata una finestra di messaggio che viene visualizzato questo messaggio:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Routine Sub](./sub-procedures.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Generazione di codice in LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Aggiunta di logica di business mediante metodi parziali](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
