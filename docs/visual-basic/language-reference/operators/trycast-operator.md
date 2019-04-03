---
title: Operatore TryCast (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: c0eea4565d5040bb00743fc7864ac15b0fccdea9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831592"
---
# <a name="trycast-operator-visual-basic"></a>Operatore TryCast (Visual Basic)
Introduce un'operazione di conversione di tipo che non viene generata un'eccezione.  
  
## <a name="remarks"></a>Note  
 Se un tentativo di conversione ha esito negativo, `CType` e `DirectCast` entrambi generano un <xref:System.InvalidCastException> errore. Ciò può influire negativamente sulle prestazioni dell'applicazione. `TryCast` Restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), in modo che anziché dover gestire una possibile eccezione, è necessario testare solo il risultato restituito su `Nothing`.  
  
 Si utilizza il `TryCast` parola chiave la stessa modalità di utilizzo il [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) e il [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) (parola chiave). Specificare un'espressione come primo argomento e un tipo per convertirlo in come secondo argomento. `TryCast` opera solo sui tipi di riferimento, ad esempio classi e interfacce. Richiede una relazione di ereditarietà o implementazione tra i due tipi. Ciò significa che un tipo deve ereditare da o implementi l'altro.  
  
## <a name="errors-and-failures"></a>Gli errori  
 `TryCast` Genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione. Ma la mancanza di un errore del compilatore non garantisce una corretta conversione. Se la conversione desiderata sia più piccolo, potrebbe non riuscire in fase di esecuzione. In questo caso `TryCast` restituisce [Nothing](../../../visual-basic/language-reference/nothing.md).  
  
## <a name="conversion-keywords"></a>Parole chiave di conversione  
 Un confronto delle parole chiave di conversione del tipo è come indicato di seguito.  
  
|Parola chiave|Tipi di dati|Relazione tra gli argomenti|Errore di run-time|  
|---|---|---|---|  
|[Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Tutti i tipi di dati|Widening o narrowing conversione deve essere definito tra i due tipi di dati|Genera un'eccezione <xref:System.InvalidCastException>|  
|[Operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md)|Tutti i tipi di dati|Un tipo deve ereditare da o implementi l'altro tipo|Genera un'eccezione <xref:System.InvalidCastException>|  
|`TryCast`|Solo i tipi di riferimento|Un tipo deve ereditare da o implementi l'altro tipo|Restituisce [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come usare `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
