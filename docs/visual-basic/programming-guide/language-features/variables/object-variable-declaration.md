---
title: Dichiarazione di variabili oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: d1964e3768124dde1deeabfada9006ff5a59def0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351807"
---
# <a name="object-variable-declaration-visual-basic"></a>Dichiarazione di variabili oggetto (Visual Basic)
Usare un'istruzione di dichiarazione normale per dichiarare una variabile oggetto. Per il tipo di dati, specificare `Object` (ovvero il [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)) o una classe più specifica da cui creare l'oggetto.  
  
 La dichiarazione di una variabile come `Object` corrisponde alla dichiarazione di <xref:System.Object?displayProperty=nameWithType>.  
  
 Quando si dichiara una variabile con una classe di oggetti specifica, può accedere a tutti i metodi e le proprietà esposte da tale classe e dalle classi da cui eredita. Se si dichiara la variabile con <xref:System.Object>, può accedere solo ai membri della classe <xref:System.Object>, a meno che non si ritorni `Option Strict Off` per consentire l'associazione tardiva.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 Per dichiarare una variabile oggetto, usare la sintassi seguente:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 Nella dichiarazione è inoltre possibile specificare [public](../../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)o [static](../../../../visual-basic/language-reference/modifiers/static.md) . Le seguenti dichiarazioni di esempio sono valide:  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>Associazione tardiva e associazione anticipata  
 A volte la classe specifica è sconosciuta fino a quando non viene eseguito il codice. In questo caso, è necessario dichiarare la variabile oggetto con il tipo di dati `Object`. In questo modo viene creato un riferimento generale a qualsiasi tipo di oggetto e la classe specifica viene assegnata in fase di esecuzione. Questa operazione viene chiamata *associazione tardiva*. Per l'associazione tardiva è necessario tempo di esecuzione aggiuntivo. Limita inoltre il codice ai metodi e alle proprietà della classe a cui è stata assegnata più di recente. Questo può causare errori di run-time se il codice tenta di accedere ai membri di una classe diversa.  
  
 Quando si conosce la classe specifica in fase di compilazione, è necessario dichiarare la variabile oggetto in modo che sia di tale classe. Questa operazione è definita *associazione anticipata*. L'associazione anticipata consente di migliorare le prestazioni e garantisce l'accesso al codice a tutti i metodi e le proprietà della classe specifica. Nelle dichiarazioni di esempio precedenti, se la variabile `objA` usa solo oggetti della classe <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, è necessario specificare `As System.Windows.Forms.Label` nella relativa dichiarazione.  
  
### <a name="advantages-of-early-binding"></a>Vantaggi offerti dall'associazione anticipata  
 La dichiarazione di una variabile oggetto come classe specifica offre diversi vantaggi:  
  
- Controllo dei tipi automatici  
  
- Accesso garantito a tutti i membri della classe specifica  
  
- Supporto di Microsoft IntelliSense nell'editor di codice  
  
- Miglioramento della leggibilità del codice  
  
- Minor numero di errori nel codice  
  
- Errori rilevati in fase di compilazione anziché in fase di esecuzione  
  
- Esecuzione di codice più veloce  
  
## <a name="access-to-object-variable-members"></a>Accesso ai membri della variabile oggetto  
 Quando `Option Strict` viene attivato `On`, una variabile oggetto può accedere solo ai metodi e alle proprietà della classe con cui viene dichiarata. Ciò è illustrato nell'esempio seguente.  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 In questo esempio `p` può usare solo i membri della classe <xref:System.Object> stessa, che non includono la proprietà `Left` . D'altra parte, `q` è stata dichiarata con il tipo <xref:System.Windows.Forms.Label>, perciò può usare tutti i metodi e le proprietà della classe <xref:System.Windows.Forms.Label> nello spazio dei nomi <xref:System.Windows.Forms> .  
  
## <a name="flexibility-of-object-variables"></a>Flessibilità delle variabili oggetto  
 Quando si utilizzano gli oggetti in una gerarchia di ereditarietà, è possibile scegliere la classe da utilizzare per dichiarare le variabili dell'oggetto. Quando si sceglie questa opzione, è necessario bilanciare la flessibilità dell'assegnazione degli oggetti rispetto all'accesso ai membri di una classe. Si consideri, ad esempio, la gerarchia di ereditarietà che conduce alla classe <xref:System.Windows.Forms.Form?displayProperty=nameWithType>:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Si supponga che l'applicazione definisca una classe Form denominata `specialForm`, che eredita dalla classe <xref:System.Windows.Forms.Form>. È possibile dichiarare una variabile oggetto che fa riferimento in modo specifico a `specialForm`, come illustrato nell'esempio riportato di seguito.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 La dichiarazione nell'esempio precedente limita la variabile `nextForm` agli oggetti della classe `specialForm`, ma rende anche tutti i metodi e le proprietà di `specialForm` disponibili per `nextForm`, oltre a tutti i membri di tutte le classi da cui `specialForm` eredita.  
  
 È possibile rendere più generale una variabile oggetto dichiarando di essere di tipo <xref:System.Windows.Forms.Form>, come illustrato nell'esempio seguente.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 La dichiarazione nell'esempio precedente consente di assegnare qualsiasi modulo nell'applicazione a `anyForm`. Tuttavia, sebbene `anyForm` possa accedere a tutti i membri della classe <xref:System.Windows.Forms.Form>, non è possibile usare i metodi o le proprietà aggiuntivi definiti per formati specifici, ad esempio `specialForm`.  
  
 Tutti i membri di una classe di base sono disponibili per le classi derivate, ma i membri aggiuntivi di una classe derivata non sono disponibili per la classe di base.  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Procedura: dichiarare una variabile oggetto e assegnarvi un oggetto in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Procedura: accedere ai membri di un oggetto](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Operatore New](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
