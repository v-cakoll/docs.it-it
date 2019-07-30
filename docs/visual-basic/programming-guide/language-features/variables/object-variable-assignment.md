---
title: Assegnazione di variabili oggetto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: 59dea45511ba8d7d10c95cf17e47981124c532e4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631060"
---
# <a name="object-variable-assignment-visual-basic"></a>Assegnazione di variabili oggetto (Visual Basic)

Utilizzare un'istruzione di assegnazione normale per assegnare un oggetto a una variabile oggetto. È possibile assegnare un'espressione di oggetto o la parola chiave [Nothing](../../../../visual-basic/language-reference/nothing.md) , come illustrato nell'esempio seguente.

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

`Nothing`indica che non è presente alcun oggetto attualmente assegnato alla variabile.

## <a name="initialization"></a>Inizializzazione

Quando viene avviata l'esecuzione del codice, le variabili oggetto `Nothing`vengono inizializzate in. Quelle le cui dichiarazioni includono l'inizializzazione vengono reinizializzate sui valori specificati durante l'esecuzione delle istruzioni di dichiarazione.

È possibile includere l'inizializzazione nella dichiarazione usando la parola chiave [New](../../../../visual-basic/language-reference/operators/new-operator.md) . Le istruzioni di dichiarazione seguenti dichiarano `ver` le variabili `testUri` oggetto e e assegnano oggetti specifici. Ogni utilizza uno dei costruttori di overload della classe appropriata per inizializzare l'oggetto.

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a>Dissociazione

L'impostazione di una variabile `Nothing` oggetto per interrompe l'associazione della variabile a un oggetto specifico. Ciò impedisce di modificare accidentalmente l'oggetto modificando la variabile. Consente inoltre di verificare se la variabile oggetto punta a un oggetto valido, come illustrato nell'esempio riportato di seguito.

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

Se l'oggetto a cui fa riferimento la variabile si trova in un'altra applicazione, questo test non è in grado di determinare se l'applicazione ha terminato o semplicemente invalidato l'oggetto.

Una variabile oggetto con un valore di `Nothing` viene anche chiamata *riferimento null*.

## <a name="current-instance"></a>Istanza corrente

L' *istanza corrente* di un oggetto è quella in cui è attualmente in esecuzione il codice. Poiché tutto il codice viene eseguito all'interno di una routine, l'istanza corrente è quella in cui è stata richiamata la procedura.

La `Me` parola chiave funge da variabile oggetto che fa riferimento all'istanza corrente. Se una routine non è [condivisa](../../../../visual-basic/language-reference/modifiers/shared.md), può usare la `Me` parola chiave per ottenere un puntatore all'istanza corrente. Le routine condivise non possono essere associate a un'istanza specifica di una classe.

L' `Me` uso di è particolarmente utile per passare l'istanza corrente a una routine in un altro modulo. Si supponga, ad esempio, di avere un numero di documenti XML e di voler aggiungere un testo standard a tutti. Nell'esempio seguente viene definita una procedura per eseguire questa operazione.

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

Ogni oggetto documento XML potrebbe quindi chiamare la stored procedure e passare l'istanza corrente come argomento. Nell'esempio che segue viene illustrato quanto descritto.

```vb
addStandardText(Me)
```

## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Procedura: Dichiarare una variabile oggetto e assegnarvi un oggetto in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Procedura: Fare in modo che una variabile oggetto non faccia riferimento ad alcuna istanza](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
