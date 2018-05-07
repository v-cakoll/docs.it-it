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
ms.openlocfilehash: fb1af7d748faac78b26177af453a0e858f9e97c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Rappresenta il valore predefinito di qualsiasi tipo di dati. Per i tipi di riferimento, il valore predefinito è il `null` riferimento. Per i tipi di valore, il valore predefinito varia a seconda se il tipo di valore è nullable.  
  
> [!NOTE]
>  Per i tipi di valore non nullable, `Nothing` in Visual Basic è diverso da `null` in c#. In Visual Basic, se si imposta una variabile di un tipo di valore non nullable `Nothing`, la variabile è impostata sul valore predefinito per il relativo tipo dichiarato. In c#, se si assegna una variabile di un tipo di valore non nullable `null`, si verifica un errore in fase di compilazione.  
  
## <a name="remarks"></a>Note  
 `Nothing` rappresenta il valore predefinito di un tipo di dati. Il valore predefinito dipende se la variabile è un tipo di valore o di un tipo di riferimento.  
  
 Una variabile di un *tipo di valore* contiene direttamente il relativo valore. Tipi di valore includono tutti i tipi di dati numerici, `Boolean`, `Char`, `Date`, tutte le strutture e tutte le enumerazioni. Una variabile di un *tipo di riferimento* archivia un riferimento a un'istanza dell'oggetto in memoria. Tipi di riferimento includono matrici, delegati, classi e le stringhe. Per altre informazioni, vedere [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Se una variabile è di un valore di tipo, il comportamento di `Nothing` varia a seconda che la variabile di un tipo di dati ammette valori null. Per rappresentare un tipo di valore nullable, aggiungere un `?` modificatore al nome del tipo. L'assegnazione di `Nothing` a una variabile che ammette valori null, il valore impostato su `null`. Per ulteriori informazioni ed esempi, vedere [tipi di valore Nullable](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Se la variabile è un tipo di valore che non ammette valori null, l'assegnazione `Nothing` per questo viene impostato il valore predefinito per il relativo tipo dichiarato. Se il tipo contiene membri variabili, sono tutti impostati sui valori predefiniti. Nell'esempio seguente viene illustrato questo per i tipi scalari.  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 Se la variabile è di un tipo riferimento, l'assegnazione `Nothing` alla variabile impostato su un `null` riferimento di tipo della variabile. Una variabile è impostata su un `null` riferimento non è associata ad alcun oggetto. Nell'esempio che segue viene illustrato quanto descritto.  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 Quando si verifica se un riferimento (o un tipo di valore nullable) è variabile `null`, non utilizzare `= Nothing` o `<> Nothing`. Utilizzare sempre `Is Nothing` o `IsNot Nothing`.  
  
 Per le stringhe in Visual Basic, è uguale a una stringa vuota `Nothing`. Pertanto, `"" = Nothing` è true.  
  
 L'esempio seguente mostra i confronti che usano il `Is` e `IsNot` operatori.  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 Se si dichiara una variabile senza utilizzare un `As` clausola e impostarlo su `Nothing`, la variabile è di tipo `Object`. Un esempio di questo oggetto è `Dim something = Nothing`. In questo caso verrà generato un errore in fase di compilazione quando `Option Strict` in e `Option Infer` è disattivata.  
  
 Quando si assegna `Nothing` a una variabile oggetto non fa riferimento a un'istanza dell'oggetto. Se la variabile ha già fatto riferimento a un'istanza, se è impostato su `Nothing` non termina l'istanza stessa. L'istanza viene terminata, e vengono rilasciate le risorse di memoria e di sistema è associate, solo dopo che il garbage collector (GC) rileva che non sono presenti riferimenti attivi.  
  
 `Nothing` è diverso dal <xref:System.DBNull> oggetto, che rappresenta un valore variant non inizializzato o una colonna del database inesistente.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Dim](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Durata degli oggetti: come creare e distruggere oggetti](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Durata in Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Operatore Is](../../visual-basic/language-reference/operators/is-operator.md)  
 [Operatore IsNot](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Tipi di valori nullable](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
