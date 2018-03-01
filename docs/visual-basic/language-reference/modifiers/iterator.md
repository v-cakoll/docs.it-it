---
title: Iteratore (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd6c0b1fa422dc4ab659d8c59472e5c098c729bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="iterator-visual-basic"></a>Iteratore (Visual Basic)
Specifica che una funzione o `Get` funzione di accesso è un iteratore.  
  
## <a name="remarks"></a>Note  
 Un *iteratore* esegue un'iterazione personalizzata su una raccolta. Un iteratore Usa il [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire ogni elemento della raccolta uno alla volta. Quando un `Yield` istruzione viene raggiunto, viene mantenuta la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.  
  
 Un iteratore può essere implementato come una funzione o come un `Get` funzione di accesso di una definizione di proprietà. Il `Iterator` modificatore viene visualizzato nella dichiarazione di funzione iteratore o `Get` della funzione di accesso.  
  
 Chiamare un iteratore dal codice client utilizzando un [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Il tipo restituito di una funzione iterator o `Get` della funzione di accesso può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Un iteratore non può avere qualsiasi `ByRef` parametri.  
  
 Un iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.  
  
 Un iteratore può essere una funzione anonima. Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Utilizzo  
 Il modificatore `Iterator` può essere usato nei contesti seguenti:  
  
-   [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una funzione iterator. La funzione iteratore ha un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo. Ogni iterazione del [per ogni](../../../visual-basic/language-reference/statements/for-each-next-statement.md) corpo dell'istruzione in `Main` crea una chiamata al `Power` funzione iteratore. Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore. Il `Iterator` modificatore è nella dichiarazione di proprietà.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 Per ulteriori esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [Iteratori](../../programming-guide/concepts/iterators.md)  
 [Istruzione Yield](../../../visual-basic/language-reference/statements/yield-statement.md)
