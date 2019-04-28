---
title: Operatore DirectCast (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 628ce4f06b91d0f514f71dea3aad8ea0fee6dccf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778547"
---
# <a name="directcast-operator-visual-basic"></a>Operatore DirectCast (Visual Basic)
Introduce un'operazione di conversione di tipo basata di ereditarietà o implementazione.  
  
## <a name="remarks"></a>Note  
 `DirectCast` non utilizzato Visual Basic le routine di supporto di run-time per la conversione, in modo da poter garantire prestazioni migliori rispetto `CType` durante la conversione da e verso il tipo di dati `Object`.  
  
 Si utilizza il `DirectCast` parola chiave simile alla modalità di utilizzo il [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) e il [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) (parola chiave). Specificare un'espressione come primo argomento e un tipo per convertirlo in come secondo argomento. `DirectCast` richiede una relazione di ereditarietà o implementazione tra i tipi di dati dei due argomenti. Ciò significa che un tipo deve ereditare da o implementi l'altro.  
  
## <a name="errors-and-failures"></a>Gli errori  
 `DirectCast` Genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione. Ma la mancanza di un errore del compilatore non garantisce una corretta conversione. Se la conversione desiderata sia più piccolo, potrebbe non riuscire in fase di esecuzione. In questo caso, il runtime genera un <xref:System.InvalidCastException> errore.  
  
## <a name="conversion-keywords"></a>Parole chiave di conversione  
 Un confronto delle parole chiave di conversione del tipo è come indicato di seguito.  
  
|Parola chiave|Tipi di dati|Relazione tra gli argomenti|Errore di run-time|  
|---|---|---|---|  
|[Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Tutti i tipi di dati|Widening o narrowing conversione deve essere definito tra i due tipi di dati|Genera un'eccezione <xref:System.InvalidCastException>|  
|`DirectCast`|Tutti i tipi di dati|Un tipo deve ereditare da o implementi l'altro tipo|Genera un'eccezione <xref:System.InvalidCastException>|  
|[Operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md)|Solo i tipi di riferimento|Un tipo deve ereditare da o implementi l'altro tipo|Restituisce [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra due utilizzi di `DirectCast`, con esito negativo in fase di esecuzione e uno che ha esito positivo.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 Nell'esempio precedente, digitare il runtime del `q` è `Double`. `CType` ha esito positivo perché `Double` può essere convertito in `Integer`. Tuttavia, il primo `DirectCast` non riesce in fase di esecuzione perché il runtime di tipo di `Double` non ha alcuna relazione di ereditarietà con `Integer`, anche se esiste una conversione. La seconda `DirectCast` ha esito positivo perché esegue la conversione dal tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control>, da cui <xref:System.Windows.Forms.Form> eredita.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
