---
title: Determinazione del tipo di un oggetto (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6d24be68ea4a9872f8f4fe89c1aabb943fbcb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="determining-object-type-visual-basic"></a>Determinazione del tipo di un oggetto (Visual Basic)
Variabili oggetto generico (vale a dire le variabili dichiarate come `Object`) possono contenere oggetti di qualsiasi classe. Quando si utilizzano variabili di tipo `Object`, potrebbe essere necessario eseguire azioni diverse in base alla classe dell'oggetto, ad esempio, alcuni oggetti potrebbero non supportano una particolare proprietà o metodo. Visual Basic fornisce due modalità per determinare quale tipo di oggetto viene archiviato in una variabile oggetto: il `TypeName` funzione e `TypeOf...Is` operatore.  
  
## <a name="typename-and-typeofis"></a>TypeName e TypeOf... È  
 Il `TypeName` funzione restituisce una stringa ed è la scelta migliore quando è necessario archiviare o visualizzare il nome della classe di un oggetto, come illustrato nel frammento di codice seguente:  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 Il `TypeOf...Is` operatore è la scelta migliore per il test del tipo di oggetto, perché è molto più veloce rispetto a un confronto di stringa equivalente con `TypeName`. Il frammento di codice seguente utilizza `TypeOf...Is` all'interno di un `If...Then...Else` istruzione:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Una parola di attenzione è in scadenza. Il `TypeOf...Is` operatore restituisce `True` se un oggetto di un tipo specifico oppure è derivato da un tipo specifico. Quasi tutte le operazioni eseguite con Visual Basic prevede gli oggetti, inclusi alcuni elementi che normalmente non vengono considerati come oggetti, ad esempio stringhe e numeri interi. Questi oggetti derivati da ed ereditano i metodi <xref:System.Object>. Quando viene passato un `Integer` e valutate con `Object`, `TypeOf...Is` operatore restituisce `True`. L'esempio seguente segnala che il parametro `InParam` sia un `Object` e `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 L'esempio seguente usa sia `TypeOf...Is` e `TypeName` per determinare il tipo di oggetto passato nel `Ctrl` argomento. Il `TestObject` chiamate di procedura `ShowType` con tre diversi tipi di controlli.  
  
#### <a name="to-run-the-example"></a>Per eseguire l'esempio  
  
1.  Creare un nuovo progetto applicazione Windows e aggiungere un <xref:System.Windows.Forms.Button> (controllo), un <xref:System.Windows.Forms.CheckBox> (controllo) e un <xref:System.Windows.Forms.RadioButton> al form.  
  
2.  Dal pulsante sul form, chiamare il `TestObject` stored procedure.  
  
3.  Aggiungere il codice seguente al form:  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [Chiamata di una proprietà o di un metodo mediante un nome di stringa](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Istruzione If...Then...Else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Tipo di dati Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
