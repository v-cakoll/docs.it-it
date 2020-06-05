---
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: bb19289c69f4c523363e88e91a58f37d232b07df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396233"
---
# <a name="iterator-visual-basic"></a>Iteratore (Visual Basic)
Specifica che una funzione o una funzione di `Get` accesso è un iteratore.  
  
## <a name="remarks"></a>Commenti  
 Un *iteratore* esegue un'iterazione personalizzata su una raccolta. Un iteratore usa l'istruzione [yield](../statements/yield-statement.md) per restituire ogni elemento della raccolta uno alla volta. Quando `Yield` viene raggiunta un'istruzione, viene mantenuta la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.  
  
 Un iteratore può essere implementato come funzione o come funzione `Get` di accesso di una definizione di proprietà. Il `Iterator` modificatore viene visualizzato nella dichiarazione della funzione o della funzione di accesso iteratore `Get` .  
  
 È possibile chiamare un iteratore dal codice client usando un [per ogni... Istruzione successiva](../statements/for-each-next-statement.md).  
  
 Il tipo restituito di una funzione o di una funzione di accesso iteratore `Get` può essere <xref:System.Collections.IEnumerable> ,, <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> .  
  
 Un iteratore non può avere `ByRef` parametri.  
  
 Un iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.  
  
 Un iteratore può essere una funzione anonima. Per ulteriori informazioni, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Uso  
 Il modificatore `Iterator` può essere usato nei contesti seguenti:  
  
- [Istruzione Function](../statements/function-statement.md)  
  
- [Property Statement](../statements/property-statement.md)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una funzione iteratore. La funzione iteratore ha un' `Yield` istruzione che si trova all'interno di un oggetto [per... Ciclo successivo](../statements/for-next-statement.md) . Ogni iterazione del corpo dell'istruzione [for each](../statements/for-each-next-statement.md) in `Main` Crea una chiamata alla `Power` funzione iteratore. Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore. Il `Iterator` modificatore si trova nella dichiarazione della proprietà.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Per altri esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iterators](../../programming-guide/concepts/iterators.md)
- [Istruzione Yield](../statements/yield-statement.md)
