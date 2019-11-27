---
title: Metodi parziali
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
ms.openlocfilehash: 7abf0565a985f1fb44fcf2bb91b9220d57a10f20
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352628"
---
# <a name="partial-methods-visual-basic"></a>Metodi parziali (Visual Basic)
I metodi parziali consentono agli sviluppatori di inserire logica personalizzata nel codice. In genere, il codice fa parte di una classe generata dalla finestra di progettazione. I metodi parziali sono definiti in una classe parziale creata da un generatore di codice e vengono comunemente usati per fornire una notifica che è stata modificata. Consentono allo sviluppatore di specificare un comportamento personalizzato in risposta alla modifica.  
  
 La finestra di progettazione del generatore di codice definisce solo la firma del metodo e una o più chiamate al metodo. Gli sviluppatori possono quindi fornire implementazioni per il metodo se desiderano personalizzare il comportamento del codice generato. Quando non viene fornita alcuna implementazione, le chiamate al metodo vengono rimosse dal compilatore, causando un sovraccarico delle prestazioni aggiuntivo.  
  
## <a name="declaration"></a>Dichiarazione  
 Il codice generato contrassegna la definizione di un metodo parziale inserendo la parola chiave `Partial` all'inizio della riga della firma.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 La definizione deve soddisfare le condizioni seguenti:  
  
- Il metodo deve essere un `Sub`, non un `Function`.  
  
- Il corpo del metodo deve essere lasciato vuoto.  
  
- Il modificatore di accesso deve essere `Private`.  
  
## <a name="implementation"></a>Implementazione  
 L'implementazione consiste principalmente nel compilare il corpo del metodo parziale. L'implementazione si trova in genere in una classe parziale separata dalla definizione e viene scritta da uno sviluppatore che desidera estendere il codice generato.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 Nell'esempio precedente la firma è stata duplicata esattamente nella dichiarazione, ma le variazioni sono possibili. In particolare, è possibile aggiungere altri modificatori, ad esempio `Overloads` o `Overrides`. È consentito un solo modificatore `Overrides`. Per ulteriori informazioni sui modificatori di metodo, vedere [istruzione secondaria](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Usa  
 È possibile chiamare un metodo parziale come si farebbe per qualsiasi altra `Sub` routine. Se il metodo è stato implementato, gli argomenti vengono valutati e viene eseguito il corpo del metodo. Tuttavia, tenere presente che l'implementazione di un metodo parziale è facoltativa. Se il metodo non è implementato, una chiamata non ha alcun effetto e le espressioni passate come argomenti al metodo non vengono valutate.  
  
## <a name="example"></a>Esempio  
 In un file denominato Product. designer. vb definire una classe `Product` con una proprietà `Quantity`.  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 In un file denominato Product. vb fornire un'implementazione per `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 Infine, nel metodo Main di un progetto, dichiarare un'istanza di `Product` e fornire un valore iniziale per la relativa proprietà `Quantity`.  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 Verrà visualizzata una finestra di messaggio in cui viene visualizzato il messaggio seguente:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Routine Sub](./sub-procedures.md)
- [Parametri facoltativi](./optional-parameters.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Generazione di codice in LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Aggiunta di logica di business mediante metodi parziali](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
