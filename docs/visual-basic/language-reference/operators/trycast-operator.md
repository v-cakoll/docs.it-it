---
title: Operatore TryCast
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 53306575cfc385039be3939fd87cf993b4509af4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348206"
---
# <a name="trycast-operator-visual-basic"></a>Operatore TryCast (Visual Basic)
Introduce un'operazione di conversione del tipo che non genera un'eccezione.  
  
## <a name="remarks"></a>Note  
 Se un tentativo di conversione non riesce, `CType` e `DirectCast` generano entrambi un errore <xref:System.InvalidCastException>. Ciò può influire negativamente sulle prestazioni dell'applicazione. `TryCast` [non restituisce nulla](../../../visual-basic/language-reference/nothing.md), quindi, anziché dover gestire una possibile eccezione, è necessario testare solo il risultato restituito rispetto a `Nothing`.  
  
 Usare la parola chiave `TryCast` nello stesso modo in cui si usano la [funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md) e la parola chiave dell' [Operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) . È possibile specificare un'espressione come primo argomento e un tipo in cui convertirla come secondo argomento. `TryCast` funziona solo sui tipi di riferimento, ad esempio le classi e le interfacce. Richiede una relazione di ereditarietà o implementazione tra i due tipi. Ciò significa che un tipo deve ereditare da o implementare l'altro.  
  
## <a name="errors-and-failures"></a>Errori ed errori  
 `TryCast` genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione. Tuttavia, la mancanza di un errore del compilatore non garantisce una conversione corretta. Se la conversione desiderata è più restrittiva, potrebbe verificarsi un errore in fase di esecuzione. In tal caso, `TryCast` [non restituisce alcun](../../../visual-basic/language-reference/nothing.md)risultato.  
  
## <a name="conversion-keywords"></a>Parole chiave di conversione  
 Di seguito è riportato un confronto delle parole chiave di conversione del tipo.  
  
|Parola chiave|Tipi di dati|Relazione tra argomenti|Errore di run-time|  
|---|---|---|---|  
|[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)|Qualsiasi tipo di dati|È necessario definire una conversione verso un tipo di dati più piccolo o più piccolo tra i due tipi di dati|Genera <xref:System.InvalidCastException>|  
|[Operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md)|Qualsiasi tipo di dati|Un tipo deve ereditare da o implementare l'altro tipo|Genera <xref:System.InvalidCastException>|  
|`TryCast`|Solo tipi di riferimento|Un tipo deve ereditare da o implementare l'altro tipo|[Non restituisce alcun](../../../visual-basic/language-reference/nothing.md) risultato|  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come usare `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
