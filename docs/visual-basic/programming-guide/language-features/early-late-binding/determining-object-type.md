---
title: Determinazione del tipo di un oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 3b1c4ad0ab4fd8d2897aff6ad9097cdc81272455
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410644"
---
# <a name="determining-object-type-visual-basic"></a>Determinazione del tipo di un oggetto (Visual Basic)
Le variabili oggetto generico, ovvero le variabili dichiarate come, `Object` possono includere oggetti da qualsiasi classe. Quando si usano variabili di tipo `Object` , potrebbe essere necessario eseguire diverse azioni in base alla classe dell'oggetto. ad esempio, alcuni oggetti potrebbero non supportare una proprietà o un metodo specifico. Visual Basic fornisce due metodi per determinare il tipo di oggetto archiviato in una variabile oggetto, ovvero la `TypeName` funzione e l' `TypeOf...Is` operatore.  
  
## <a name="typename-and-typeofis"></a>TypeName e TypeOf... È  
 La `TypeName` funzione restituisce una stringa ed è la scelta migliore quando è necessario archiviare o visualizzare il nome della classe di un oggetto, come illustrato nel frammento di codice seguente:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 L' `TypeOf...Is` operatore è la scelta migliore per testare il tipo di un oggetto, perché è molto più veloce rispetto a un confronto di stringhe equivalente usando `TypeName` . Nel frammento di codice seguente viene utilizzato `TypeOf...Is` all'interno di un' `If...Then...Else` istruzione:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 È prevista una parola di attenzione. L' `TypeOf...Is` operatore restituisce `True` se un oggetto è di un tipo specifico o è derivato da un tipo specifico. Quasi tutte le operazioni eseguite con Visual Basic coinvolgono oggetti, che includono alcuni elementi che in genere non sono considerati oggetti, ad esempio stringhe e numeri interi. Questi oggetti sono derivati da ed ereditano metodi da <xref:System.Object> . Quando viene passato un oggetto `Integer` e valutato con `Object` , l' `TypeOf...Is` operatore restituisce `True` . Nell'esempio seguente viene segnalato che il parametro `InParam` è un oggetto `Object` e un oggetto `Integer` :  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 Nell'esempio seguente vengono usati sia `TypeOf...Is` che `TypeName` per determinare il tipo di oggetto passato nell' `Ctrl` argomento. La `TestObject` procedura chiama `ShowType` con tre tipi diversi di controlli.  
  
#### <a name="to-run-the-example"></a>Per eseguire l'esempio  
  
1. Creare un nuovo progetto di applicazione Windows e aggiungere un controllo <xref:System.Windows.Forms.Button> , un controllo <xref:System.Windows.Forms.CheckBox> e un <xref:System.Windows.Forms.RadioButton> controllo al form.  
  
2. Dal pulsante nel form, chiamare la `TestObject` procedura.  
  
3. Aggiungere il codice seguente al form:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Chiamata di una proprietà o di un metodo mediante un nome di stringa](calling-a-property-or-method-using-a-string-name.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Istruzione If...Then...Else](../../../language-reference/statements/if-then-else-statement.md)
- [Tipo di dati String](../../../language-reference/data-types/string-data-type.md)
- [Tipo di dati Integer](../../../language-reference/data-types/integer-data-type.md)
