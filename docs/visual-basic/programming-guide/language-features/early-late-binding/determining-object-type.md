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
ms.openlocfilehash: a77cc0603a0b61f58a4aa703c4b1e6ef4c26729c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345191"
---
# <a name="determining-object-type-visual-basic"></a>Determinazione del tipo di un oggetto (Visual Basic)
Le variabili oggetto generico (ovvero le variabili dichiarate come `Object`) possono includere oggetti da qualsiasi classe. Quando si usano variabili di tipo `Object`, potrebbe essere necessario eseguire diverse azioni in base alla classe dell'oggetto. alcuni oggetti, ad esempio, potrebbero non supportare una proprietà o un metodo specifico. Visual Basic fornisce due metodi per determinare il tipo di oggetto archiviato in una variabile oggetto, ovvero la funzione `TypeName` e l'operatore di `TypeOf...Is`.  
  
## <a name="typename-and-typeofis"></a>TypeName e TypeOf... È  
 La funzione `TypeName` restituisce una stringa ed è la scelta migliore quando è necessario archiviare o visualizzare il nome della classe di un oggetto, come illustrato nel frammento di codice seguente:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 L'operatore `TypeOf...Is` è la scelta migliore per il test di un tipo di oggetto, perché è molto più veloce rispetto a un confronto di stringhe equivalente con `TypeName`. Il frammento di codice seguente usa `TypeOf...Is` all'interno di un'istruzione `If...Then...Else`:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 È prevista una parola di attenzione. L'operatore `TypeOf...Is` restituisce `True` se un oggetto è di un tipo specifico o è derivato da un tipo specifico. Quasi tutte le operazioni eseguite con Visual Basic coinvolgono oggetti, che includono alcuni elementi che in genere non sono considerati oggetti, ad esempio stringhe e numeri interi. Questi oggetti sono derivati da ed ereditano metodi da <xref:System.Object>. Quando viene passato un `Integer` e valutato con `Object`, l'operatore `TypeOf...Is` restituisce `True`. Nell'esempio riportato di seguito viene segnalato che il `InParam` del parametro è sia `Object` che `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 Nell'esempio seguente vengono usati sia `TypeOf...Is` sia `TypeName` per determinare il tipo di oggetto passato nell'argomento `Ctrl`. La procedura `TestObject` chiama `ShowType` con tre tipi diversi di controlli.  
  
#### <a name="to-run-the-example"></a>Per eseguire l'esempio  
  
1. Creare un nuovo progetto di applicazione Windows e aggiungere un controllo <xref:System.Windows.Forms.Button>, un controllo <xref:System.Windows.Forms.CheckBox> e un controllo <xref:System.Windows.Forms.RadioButton> al form.  
  
2. Dal pulsante sul form, chiamare la procedura `TestObject`.  
  
3. Aggiungere il codice seguente al form:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Chiamata di una proprietà o di un metodo mediante un nome di stringa](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Istruzione If...Then...Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Tipo di dati Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
