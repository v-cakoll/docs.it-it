---
title: Operatore TryCast
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 8f0d4f612cd5a96e0b0ab7305c41e00790613cc8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406385"
---
# <a name="trycast-operator-visual-basic"></a>Operatore TryCast (Visual Basic)
Introduce un'operazione di conversione del tipo che non genera un'eccezione.  
  
## <a name="remarks"></a>Commenti  
 Se un tentativo di conversione ha esito negativo `CType` e viene `DirectCast` generato un <xref:System.InvalidCastException> errore. Ciò può influire negativamente sulle prestazioni dell'applicazione. `TryCast`[non restituisce nulla](../nothing.md), quindi, anziché dover gestire una possibile eccezione, è necessario testare solo il risultato restituito `Nothing` .  
  
 Usare la `TryCast` parola chiave nello stesso modo in cui si usano la [funzione CType](../functions/ctype-function.md) e la parola chiave dell' [Operatore DirectCast](directcast-operator.md) . È possibile specificare un'espressione come primo argomento e un tipo in cui convertirla come secondo argomento. `TryCast`opera solo sui tipi di riferimento, ad esempio le classi e le interfacce. Richiede una relazione di ereditarietà o implementazione tra i due tipi. Ciò significa che un tipo deve ereditare da o implementare l'altro.  
  
## <a name="errors-and-failures"></a>Errori ed errori  
 `TryCast`genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione. Tuttavia, la mancanza di un errore del compilatore non garantisce una conversione corretta. Se la conversione desiderata è più restrittiva, potrebbe verificarsi un errore in fase di esecuzione. In tal caso, `TryCast` non viene restituito [alcun](../nothing.md)risultato.  
  
## <a name="conversion-keywords"></a>Parole chiave di conversione  
 Di seguito è riportato un confronto delle parole chiave di conversione del tipo.  
  
|Parola chiave|Tipi di dati|Relazione tra argomenti|Errore di run-time|  
|---|---|---|---|  
|[CType Function](../functions/ctype-function.md)|Qualsiasi tipo di dati|È necessario definire una conversione verso un tipo di dati più piccolo o più piccolo tra i due tipi di dati|Genera<xref:System.InvalidCastException>|  
|[Operatore DirectCast](directcast-operator.md)|Qualsiasi tipo di dati|Un tipo deve ereditare da o implementare l'altro tipo|Genera<xref:System.InvalidCastException>|  
|`TryCast`|Solo tipi di riferimento|Un tipo deve ereditare da o implementare l'altro tipo|[Non restituisce alcun](../nothing.md) risultato|  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come usare `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
