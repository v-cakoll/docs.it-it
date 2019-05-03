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
ms.openlocfilehash: 97c651dbcc657fbab0706c9a959bd0031c0fe343
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778625"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Rappresenta il valore predefinito di qualsiasi tipo di dati. Per i tipi di riferimento, il valore predefinito è il `null` riferimento. Per i tipi di valore, il valore predefinito dipende dal fatto che il tipo di valore è nullable.  
  
> [!NOTE]
>  Per i tipi di valore non nullable `Nothing` in Visual Basic è diverso da `null` in C#. In Visual Basic, se si imposta una variabile di un tipo di valore non nullable per `Nothing`, la variabile è impostata sul valore predefinito per il relativo tipo dichiarato. In C#, se si assegna una variabile di un tipo valore non nullable `null`, si verifica un errore in fase di compilazione.  
  
## <a name="remarks"></a>Note  
 `Nothing` rappresenta il valore predefinito di un tipo di dati. Il valore predefinito dipende dal fatto che la variabile è di un tipo valore o di un tipo riferimento.  
  
 Una variabile di un *tipo di valore* contiene direttamente il relativo valore. Tipi di valore includono tutti i tipi di dati numerici `Boolean`, `Char`, `Date`, tutte le strutture e tutte le enumerazioni. Una variabile di un *fanno riferimento a tipo* archivia un riferimento a un'istanza dell'oggetto in memoria. I tipi di riferimento includono classi, delegati, matrici e stringhe. Per altre informazioni, vedere [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Se una variabile è di un valore di tipo, il comportamento di `Nothing` varia a seconda che la variabile di un tipo di dati ammette valori null. Per rappresentare un tipo valore nullable, aggiungere un `?` modificatore al nome del tipo. Assegnazione `Nothing` a una variabile che ammette valori null, il valore impostato su `null`. Per altre informazioni ed esempi, vedere [tipi di valore Nullable](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Se la variabile è di un tipo di valore che non ammette valori null, l'assegnazione `Nothing` a lo imposta sul valore predefinito per il relativo tipo dichiarato. Se tale tipo contiene membri variabili, sono tutti impostati sui valori predefiniti. Nell'esempio seguente viene illustrato ciò per i tipi scalari.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 Se la variabile è di un tipo riferimento, assegnando `Nothing` alla variabile lo imposta su un `null` riferimento di tipo della variabile. Una variabile che è impostata su un `null` riferimento non è associata ad alcun oggetto. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 Quando si verifica se un riferimento (o un tipo valore nullable) è variabile `null`, non usare `= Nothing` o `<> Nothing`. Usare sempre `Is Nothing` o `IsNot Nothing`.  
  
 Per le stringhe in Visual Basic, è uguale a una stringa vuota `Nothing`. Pertanto, `"" = Nothing` è true.  
  
 L'esempio seguente mostra i confronti che usano il `Is` e `IsNot` operatori.  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 Se si dichiara una variabile senza usare un `As` clausola e impostarla su `Nothing`, la variabile è di tipo `Object`. Un esempio di ciò è `Dim something = Nothing`. In questo caso verrà generato un errore in fase di compilazione quando `Option Strict` si trova in e `Option Infer` è disattivata.  
  
 Quando si assegnano `Nothing` a una variabile oggetto, non è più fa riferimento a qualsiasi istanza dell'oggetto. Se la variabile ha già fatto riferimento a un'istanza, impostandola su `Nothing` non termina l'istanza stessa. L'istanza viene terminata e vengono rilasciate le risorse di memoria e di sistema associate, solo dopo che il garbage collector (GC) rileva che non sono presenti riferimenti attivi.  
  
 `Nothing` è diverso dal <xref:System.DBNull> oggetto che rappresenta una variante non inizializzata o una colonna del database inesistente.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Dim](../../visual-basic/language-reference/statements/dim-statement.md)
- [Durata degli oggetti: Come gli oggetti vengono creati ed eliminati](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Durata in Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Operatore Is](../../visual-basic/language-reference/operators/is-operator.md)
- [Operatore IsNot](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Tipi di valori nullable](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
