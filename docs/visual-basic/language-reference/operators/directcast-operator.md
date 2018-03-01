---
title: Operatore DirectCast (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a>Operatore DirectCast (Visual Basic)
Introduce un'operazione di conversione di tipo in base a ereditarietà o implementazione.  
  
## <a name="remarks"></a>Note  
 `DirectCast`non utilizzare Visual Basic le routine di supporto in fase di esecuzione per la conversione, in modo da poter garantire prestazioni migliori rispetto `CType` durante la conversione da e verso il tipo di dati `Object`.  
  
 Utilizzare il `DirectCast` (parola chiave) simile alla modalità di utilizzo di [CType (funzione)](../../../visual-basic/language-reference/functions/ctype-function.md) e [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) (parola chiave). Specificare un'espressione come primo argomento e un tipo per convertirlo in come secondo argomento. `DirectCast`richiede una relazione di ereditarietà o implementazione tra i tipi di dati dei due argomenti. Ciò significa che un tipo deve ereditare da o implementare l'altro.  
  
## <a name="errors-and-failures"></a>Errori e problemi  
 `DirectCast`Genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione. Tuttavia, la mancanza di un errore del compilatore non garantisce una corretta conversione. Se la conversione desiderata è più piccolo, potrebbe non riuscire in fase di esecuzione. In questo caso, il runtime genera un <xref:System.InvalidCastException> errore.  
  
## <a name="conversion-keywords"></a>Parole chiave di conversione  
 Un confronto delle parole chiave di conversione del tipo è come indicato di seguito.  
  
|Parola chiave|Tipi di dati|Relazione tra gli argomenti|Errore di run-time|  
|---|---|---|---|  
|[Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)|I tipi di dati|Widening o narrowing conversione deve essere definito tra i due tipi di dati|Genera un'eccezione<xref:System.InvalidCastException>|  
|`DirectCast`|I tipi di dati|Un tipo deve ereditare da o implementare l'altro tipo|Genera un'eccezione<xref:System.InvalidCastException>|  
|[Operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md)|Solo i tipi di riferimento|Un tipo deve ereditare da o implementare l'altro tipo|Restituisce [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra due utilizzi di `DirectCast`, con esito negativo in fase di esecuzione e una che ha esito positivo.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 Nell'esempio precedente, il runtime tipo `q` è `Double`. `CType`ha esito positivo perché `Double` può essere convertito in `Integer`. Tuttavia, il primo `DirectCast` ha esito negativo in fase di esecuzione perché il tipo di runtime di `Double` non ha alcuna relazione di ereditarietà con `Integer`, anche se esiste una conversione. Il secondo `DirectCast` ha esito positivo perché esegue la conversione dal tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control>, da cui <xref:System.Windows.Forms.Form> eredita.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
