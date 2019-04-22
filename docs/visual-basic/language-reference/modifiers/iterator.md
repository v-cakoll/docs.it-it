---
title: Iteratore (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 499949d1f4c20e1f465355bd076ba39f1496779b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822700"
---
# <a name="iterator-visual-basic"></a>Iteratore (Visual Basic)
Specifica che una funzione o `Get` della funzione di accesso è un iteratore.  
  
## <a name="remarks"></a>Note  
 Un' *iteratore* esegue un'iterazione personalizzata su una raccolta. Un iteratore Usa il [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire ogni elemento nella raccolta uno alla volta. Quando un `Yield` viene raggiunta l'istruzione, viene mantenuta la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.  
  
 Un iteratore può essere implementato come una funzione o un `Get` funzione di accesso di una definizione di proprietà. Il `Iterator` modificatore presente nella dichiarazione della funzione iteratore o `Get` della funzione di accesso.  
  
 Chiamare un iteratore dal codice client usando un [For Each... Istruzione Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Il tipo restituito di una funzione iteratore o `Get` funzione di accesso può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Un iteratore non può contenere `ByRef` parametri.  
  
 Un iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.  
  
 Un iteratore può essere una funzione anonima. Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Utilizzo  
 Il modificatore `Iterator` può essere usato nei contesti seguenti:  
  
-   [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra una funzione iteratore. La funzione iteratore ha un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo. Ogni iterazione del [per ognuno](../../../visual-basic/language-reference/statements/for-each-next-statement.md) nel corpo dell'istruzione `Main` crea una chiamata al `Power` funzione iteratore. Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore. Il `Iterator` modificatore è nella dichiarazione di proprietà.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Per altri esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iteratori](../../programming-guide/concepts/iterators.md)
- [Istruzione Yield](../../../visual-basic/language-reference/statements/yield-statement.md)
