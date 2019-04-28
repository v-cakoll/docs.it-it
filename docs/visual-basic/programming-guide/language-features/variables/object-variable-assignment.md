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
ms.openlocfilehash: dff1b9bb9e87f827663786cac3f33531db41b2c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757066"
---
# <a name="object-variable-assignment-visual-basic"></a>Assegnazione di variabili oggetto (Visual Basic)
Utilizzare una normale istruzione di assegnazione per assegnare un oggetto a una variabile oggetto. È possibile assegnare un'espressione di oggetto o il [Nothing](../../../../visual-basic/language-reference/nothing.md) (parola chiave), come illustrato nell'esempio seguente viene illustrato.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` indica che è presente alcun oggetto attualmente assegnato alla variabile.  
  
## <a name="initialization"></a>Inizializzazione  
 Quando il codice inizia l'esecuzione, l'oggetto le variabili vengono inizializzate su `Nothing`. Quelli il cui dichiarazioni includono inizializzazione vengono reinizializzati per i valori specificati quando vengono eseguite le istruzioni di dichiarazione.  
  
 È possibile includere inizializzazione nella dichiarazione di utilizzando il [New](../../../../visual-basic/language-reference/operators/new-operator.md) (parola chiave). Le seguenti istruzioni di dichiarazione dichiarano le variabili di oggetto `testUri` e `ver` e assegnare loro oggetti specifici. Ognuno utilizza uno dei costruttori di overload della classe appropriata per inizializzare l'oggetto.  
  
```  
Dim testUri As New System.Uri("https://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a>Annullamento dell'associazione  
 L'impostazione di una variabile oggetto `Nothing` interrompe l'associazione della variabile con un oggetto specifico. Ciò impedisce di modificare accidentalmente l'oggetto modificando la variabile. Consente inoltre di verificare se la variabile oggetto fa riferimento a un oggetto valido, come illustrato nell'esempio seguente.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 Se l'oggetto che fa riferimento la variabile è in un'altra applicazione, questo test non è possibile determinare se quell'applicazione ha terminato o semplicemente invalidato l'oggetto.  
  
 Una variabile oggetto con il valore `Nothing` viene chiamato anche un *riferimento null*.  
  
## <a name="current-instance"></a>Istanza corrente  
 Il *istanza corrente* è quello in cui è attualmente in esecuzione il codice di un oggetto. Poiché tutto il codice viene eseguito all'interno di una routine, l'istanza corrente è quello in cui è stata richiamata la procedura.  
  
 Il `Me` parola chiave agisce come una variabile oggetto che fa riferimento all'istanza corrente. Se non è una routine [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), può usare il `Me` parola chiave per ottenere un puntatore all'istanza corrente. Le procedure condivise non possono essere associate a un'istanza specifica di una classe.  
  
 Usando `Me` è particolarmente utile per passare l'istanza corrente a una routine in un altro modulo. Si supponga, ad esempio, che è presente un numero di documenti XML e si vogliono aggiungere del testo standard di tutti gli elementi. Nell'esempio seguente definisce una routine a questo scopo.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 Ogni oggetto del documento XML può quindi chiamare la routine e passare la propria istanza corrente come argomento. Nell'esempio che segue viene illustrato quanto descritto.  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Procedura: Dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Procedura: Impostare una variabile oggetto non fa riferimento a qualsiasi istanza](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
