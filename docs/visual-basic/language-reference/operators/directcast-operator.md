---
title: Operatore DirectCast
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 8ea29b80cf27bbb2c21a8cebbfaa0a294e05f11d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331313"
---
# <a name="directcast-operator-visual-basic"></a>Operatore DirectCast (Visual Basic)
Introduce un'operazione di conversione del tipo basata sull'ereditarietà o sull'implementazione.  
  
## <a name="remarks"></a>Note  
 `DirectCast` non usa le routine di supporto della fase di esecuzione Visual Basic per la conversione, pertanto può fornire prestazioni migliori rispetto a `CType` durante la conversione da e verso il tipo di dati `Object`.  
  
 Usare la parola chiave `DirectCast` simile a quella usata per la [funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md) e la parola chiave dell' [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) . È possibile specificare un'espressione come primo argomento e un tipo in cui convertirla come secondo argomento. `DirectCast` richiede una relazione di ereditarietà o implementazione tra i tipi di dati dei due argomenti. Ciò significa che un tipo deve ereditare da o implementare l'altro.  
  
## <a name="errors-and-failures"></a>Errori ed errori  
 `DirectCast` genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione. Tuttavia, la mancanza di un errore del compilatore non garantisce una conversione corretta. Se la conversione desiderata è più restrittiva, potrebbe verificarsi un errore in fase di esecuzione. In tal caso, il runtime genera un errore di <xref:System.InvalidCastException>.  
  
## <a name="conversion-keywords"></a>Parole chiave di conversione  
 Di seguito è riportato un confronto delle parole chiave di conversione del tipo.  
  
|Parola chiave|Tipi di dati|Relazione tra argomenti|Errore di run-time|  
|---|---|---|---|  
|[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)|Qualsiasi tipo di dati|È necessario definire una conversione verso un tipo di dati più piccolo o più piccolo tra i due tipi di dati|Genera <xref:System.InvalidCastException>|  
|`DirectCast`|Qualsiasi tipo di dati|Un tipo deve ereditare da o implementare l'altro tipo|Genera <xref:System.InvalidCastException>|  
|[Operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md)|Solo tipi di riferimento|Un tipo deve ereditare da o implementare l'altro tipo|[Non restituisce alcun](../../../visual-basic/language-reference/nothing.md) risultato|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrati due utilizzi di `DirectCast`, uno che non riesce in fase di esecuzione e uno che ha esito positivo.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 Nell'esempio precedente, il tipo di runtime di `q` è `Double`. `CType` ha esito positivo perché `Double` può essere convertito in `Integer`. Tuttavia, la prima `DirectCast` non riesce in fase di esecuzione perché il tipo di runtime di `Double` non ha una relazione di ereditarietà con `Integer`, anche se esiste una conversione. Il secondo `DirectCast` ha esito positivo perché converte dal tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control>, da cui <xref:System.Windows.Forms.Form> eredita.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
