---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 12c88db49dc7723fc269195e7d174bfa822c64d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963753"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Rappresenta il valore predefinito di qualsiasi tipo di dati. Per i tipi di riferimento, il valore predefinito `null` è il riferimento. Per i tipi di valore, il valore predefinito dipende dal tipo di valore che ammette valori null.  
  
> [!NOTE]
> Per i tipi di valore non Nullable `Nothing` , in Visual Basic differisce `null` da C#in. In Visual Basic, se si imposta una variabile di un tipo di valore non nullable su `Nothing`, la variabile viene impostata sul valore predefinito per il tipo dichiarato. In C#, se si assegna una variabile di un tipo di valore non nullable a `null`, si verifica un errore in fase di compilazione.  
  
## <a name="remarks"></a>Note  
 `Nothing`rappresenta il valore predefinito di un tipo di dati. Il valore predefinito dipende dal fatto che la variabile sia di un tipo di valore o di un tipo di riferimento.  
  
 Una variabile di un *tipo di valore* contiene direttamente il relativo valore. I tipi di valore includono tutti i tipi `Boolean`di `Char`dati `Date`numerici,,,, tutte le strutture e tutte le enumerazioni. Una variabile di un *tipo riferimento* archivia un riferimento a un'istanza dell'oggetto in memoria. I tipi di riferimento includono classi, matrici, delegati e stringhe. Per altre informazioni, vedere [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Se una variabile è di un tipo valore, il comportamento di `Nothing` varia a seconda che la variabile sia di un tipo di dati nullable. Per rappresentare un tipo di valore Nullable, aggiungere `?` un modificatore al nome del tipo. Se si assegna a una variabile nullable, il valore viene impostato su `null`. `Nothing` Per ulteriori informazioni ed esempi, vedere [tipi di valore Nullable](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Se una variabile è di un tipo valore che non ammette valori null, l' `Nothing` assegnazione a tale variabile lo imposta sul valore predefinito per il tipo dichiarato. Se il tipo contiene membri variabili, vengono impostati tutti sui rispettivi valori predefiniti. Nell'esempio seguente viene illustrato questo per i tipi scalari.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 Se una variabile è di un tipo riferimento, l'assegnazione `Nothing` alla variabile lo imposta su un `null` riferimento del tipo della variabile. Una variabile impostata su un `null` riferimento non è associata ad alcun oggetto. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 Quando si verifica se una variabile di riferimento (o tipo di valore `null`Nullable) è, `= Nothing` non `<> Nothing`usare o. Usare `Is Nothing` sempre o `IsNot Nothing`.  
  
 Per le stringhe in Visual Basic, la stringa vuota è `Nothing`uguale a. Pertanto, `"" = Nothing` è true.  
  
 Nell'esempio seguente vengono illustrati i confronti `IsNot` che utilizzano gli `Is` operatori e.  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 Se si dichiara una variabile senza usare una `As` clausola e la si imposta `Nothing`su, la variabile ha un tipo `Object`di. Un esempio è `Dim something = Nothing`. In questo caso si verifica un errore in fase di `Option Strict` compilazione quando è `Option Infer` attivo ed è disattivato.  
  
 Quando si assegna `Nothing` a una variabile oggetto, non fa più riferimento a un'istanza dell'oggetto. Se la variabile ha precedentemente fatto riferimento a un'istanza, impostarla `Nothing` su non termina l'istanza stessa. L'istanza viene terminata e le risorse di memoria e di sistema associate vengono rilasciate, solo dopo che il Garbage Collector (GC) rileva che non sono presenti riferimenti attivi rimanenti.  
  
 `Nothing`differisce dall' <xref:System.DBNull> oggetto, che rappresenta una variante non inizializzata o una colonna di database non esistente.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Dim](../../visual-basic/language-reference/statements/dim-statement.md)
- [Durata degli oggetti: Come vengono creati ed eliminati gli oggetti](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Durata in Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Operatore Is](../../visual-basic/language-reference/operators/is-operator.md)
- [Operatore IsNot](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Tipi di valori nullable](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
