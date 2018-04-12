---
title: Operatore TryCast (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a>Operatore TryCast (Visual Basic)
Introduce un'operazione di conversione di tipo che non viene generata un'eccezione.  
  
## <a name="remarks"></a>Note  
 Se un tentativo di conversione non riesce, `CType` e `DirectCast` generano entrambi un <xref:System.InvalidCastException> errore. Questo può influire negativamente sulle prestazioni dell'applicazione. `TryCast`Restituisce [nulla](../../../visual-basic/language-reference/nothing.md), in modo che, anziché dover gestire una possibile eccezione, è necessario testare solo il risultato restituito contro `Nothing`.  
  
 Utilizzare il `TryCast` parola chiave la stessa modalità di utilizzo il [CType (funzione)](../../../visual-basic/language-reference/functions/ctype-function.md) e [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) (parola chiave). Specificare un'espressione come primo argomento e un tipo per convertirlo in come secondo argomento. `TryCast`opera solo sui tipi di riferimento, ad esempio le classi e interfacce. Richiede una relazione di ereditarietà o implementazione tra i due tipi. Ciò significa che un tipo deve ereditare da o implementare l'altro.  
  
## <a name="errors-and-failures"></a>Errori e problemi  
 `TryCast`Genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione. Tuttavia, la mancanza di un errore del compilatore non garantisce una corretta conversione. Se la conversione desiderata è più piccolo, potrebbe non riuscire in fase di esecuzione. In questo caso, `TryCast` restituisce [nulla](../../../visual-basic/language-reference/nothing.md).  
  
## <a name="conversion-keywords"></a>Parole chiave di conversione  
 Un confronto delle parole chiave di conversione del tipo è come indicato di seguito.  
  
|Parola chiave|Tipi di dati|Relazione tra gli argomenti|Errore di run-time|  
|---|---|---|---|  
|[Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)|I tipi di dati|Widening o narrowing conversione deve essere definito tra i due tipi di dati|Genera un'eccezione<xref:System.InvalidCastException>|  
|[Operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md)|I tipi di dati|Un tipo deve ereditare da o implementare l'altro tipo|Genera un'eccezione<xref:System.InvalidCastException>|  
|`TryCast`|Solo i tipi di riferimento|Un tipo deve ereditare da o implementare l'altro tipo|Restituisce [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come usare `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
