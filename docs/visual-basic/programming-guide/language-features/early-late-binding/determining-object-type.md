---
title: Determinazione del tipo di un oggetto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 4014bef2e0c27a0f6a684bc1ed95019f392062a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050519"
---
# <a name="determining-object-type-visual-basic"></a>Determinazione del tipo di un oggetto (Visual Basic)
Variabili oggetto generico (ovvero, le variabili dichiarate come `Object`) possono contenere oggetti di qualsiasi classe. Quando si usano le variabili di tipo `Object`, potrebbe essere necessario eseguire azioni diverse in base alla classe dell'oggetto, ad esempio, alcuni oggetti potrebbero non supportare una determinata proprietà o metodo. Visual Basic offre due modi per determinare quale tipo di oggetto viene archiviato in una variabile oggetto: il `TypeName` funzione e `TypeOf...Is` operatore.  
  
## <a name="typename-and-typeofis"></a>TypeName e TypeOf... È  
 Il `TypeName` funzione restituisce una stringa ed è la scelta migliore quando è necessario archiviare o visualizzare il nome della classe di un oggetto, come illustrato nel frammento di codice seguente:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 Il `TypeOf...Is` operatore è la scelta migliore per il test di un tipo di oggetto, perché è molto più veloce rispetto a un confronto di stringa equivalente usando `TypeName`. Il frammento di codice seguente viene utilizzata `TypeOf...Is` all'interno di un `If...Then...Else` istruzione:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 Precisazione importante è dovuta qui. Il `TypeOf...Is` operatore restituisce `True` se un oggetto è di un tipo specifico oppure è derivato da un tipo specifico. Quasi tutte le operazioni eseguite con Visual Basic prevede gli oggetti che includono alcuni elementi che normalmente non vengono considerati come oggetti, ad esempio stringhe e numeri interi. Questi oggetti derivano dalla ed ereditano i metodi <xref:System.Object>. Quando viene passato un `Integer` e valutati con `Object`, il `TypeOf...Is` operatore restituisce `True`. L'esempio seguente segnala che il parametro `InParam` sia un' `Object` e un `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 L'esempio seguente usa entrambe `TypeOf...Is` e `TypeName` per determinare il tipo dell'oggetto passato nel `Ctrl` argomento. Il `TestObject` le chiamate di procedura `ShowType` con tre tipi diversi di controlli.  
  
#### <a name="to-run-the-example"></a>Per eseguire l'esempio  
  
1. Creare un nuovo progetto applicazione Windows e aggiungere una <xref:System.Windows.Forms.Button> (controllo), una <xref:System.Windows.Forms.CheckBox> (controllo) e un <xref:System.Windows.Forms.RadioButton> controllo al form.  
  
2. Dal pulsante sul form, chiamare il `TestObject` procedure.  
  
3. Aggiungere il codice seguente al form:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Chiamata di una proprietà o di un metodo mediante un nome di stringa](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Istruzione If...Then...Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Tipo di dati Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
