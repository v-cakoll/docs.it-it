---
title: Dichiarazione di variabili oggetto (Visual Basic)
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
ms.openlocfilehash: 4a3ef3a8254153fa8695ffacd9829ca9316d77a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959978"
---
# <a name="object-variable-declaration-visual-basic"></a>Dichiarazione di variabili oggetto (Visual Basic)
Utilizzare un'istruzione di dichiarazione normale per dichiarare una variabile oggetto. Per il tipo di dati è specificare `Object` (vale a dire la [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) o in una classe più specifica da cui l'oggetto deve essere creata.  
  
 Dichiarazione di una variabile come `Object` equivale dichiararla come <xref:System.Object?displayProperty=nameWithType>.  
  
 Quando si dichiara una variabile con una classe di oggetto specifico, è possibile accedere a tutti i metodi e proprietà esposte da quella classe e le classi da cui eredita. Se si dichiara la variabile con <xref:System.Object>, è possibile accedere solo i membri del <xref:System.Object> classe, a meno che non si attiva `Option Strict Off` per consentire l'associazione tardiva.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 Per dichiarare una variabile oggetto, usare la sintassi seguente:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 È inoltre possibile specificare [pubbliche](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [privata](../../../../visual-basic/language-reference/modifiers/private.md), [condiviso](../../../../visual-basic/language-reference/modifiers/shared.md), oppure [statici](../../../../visual-basic/language-reference/modifiers/static.md) nella dichiarazione. Le dichiarazioni di esempio seguenti sono valide:  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>Associazione tardiva e l'associazione anticipata  
 In alcuni casi la classe specifica è sconosciuta fino a quando non viene eseguito il codice. In questo caso, è necessario dichiarare la variabile oggetto con il `Object` tipo di dati. Verrà creato un riferimento generico a qualsiasi tipo di oggetto e la classe specifica viene assegnata in fase di esecuzione. Questa operazione viene definita *associazione tardiva*. L'associazione tardiva richiede ulteriore tempo di esecuzione. Limita inoltre il codice ai metodi e proprietà della classe che più di recente è stato assegnato a esso. Ciò può causare errori di run-time se il codice tenta di accedere ai membri di un'altra classe.  
  
 Quando si conosce la classe specifica in fase di compilazione, è necessario dichiarare la variabile oggetto di tale classe. Questa operazione è definita *associazione anticipata*. Associazione anticipata migliora le prestazioni e garantisce l'accesso di codice per tutti i metodi e proprietà della classe specifica. Nelle dichiarazioni di esempio precedente, se la variabile `objA` Usa solo gli oggetti della classe <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, è necessario specificare `As System.Windows.Forms.Label` nella relativa dichiarazione.  
  
### <a name="advantages-of-early-binding"></a>Vantaggi offerti dall'associazione anticipata  
 Si dichiara una variabile oggetto come una classe specifica offre diversi vantaggi:  
  
- Controllo automatico dei tipi  
  
- È garantito l'accesso a tutti i membri della classe specifico  
  
- Supporto tecnico Microsoft IntelliSense nell'Editor del codice  
  
- Migliorare la leggibilità del codice  
  
- Numero di errori nel codice  
  
- Gli errori rilevati in fase di compilazione anziché di tempo di esecuzione  
  
- Esecuzione di codice più veloce  
  
## <a name="access-to-object-variable-members"></a>Accesso ai membri delle variabili oggetto  
 Quando `Option Strict` è attivato `On`, una variabile oggetto può accedere solo ai metodi e proprietà della classe con cui è dichiarata. Questa condizione è illustrata nell'esempio seguente.  
  
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
  
## <a name="flexibility-of-object-variables"></a>Flessibilità di variabili oggetto  
 Quando si lavora con gli oggetti in una gerarchia di ereditarietà, è possibile scegliere quale classe usare per dichiarare le variabili oggetto. Effettuare questa scelta, è necessario bilanciare la flessibilità dell'assegnazione di oggetti e l'accesso ai membri di una classe. Ad esempio, prendere in considerazione la gerarchia di ereditarietà comporta il <xref:System.Windows.Forms.Form?displayProperty=nameWithType> classe:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Si supponga che l'applicazione definisce una classe del modulo chiamata `specialForm`, che eredita dalla classe <xref:System.Windows.Forms.Form>. È possibile dichiarare una variabile oggetto che fa riferimento in maniera specifica `specialForm`, come illustrato nell'esempio seguente.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 La dichiarazione dell'esempio precedente consente di limitare la variabile `nextForm` agli oggetti della classe `specialForm`, ma rende anche tutti i metodi e proprietà di `specialForm` disponibili per `nextForm`, nonché per tutti i membri di tutte le classi da cui `specialForm` eredita.  
  
 È possibile apportare una variabile oggetto più generale dichiarando la variabile di tipo <xref:System.Windows.Forms.Form>, come illustrato nell'esempio seguente.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 La dichiarazione dell'esempio precedente consente di assegnare qualsiasi form nell'applicazione per `anyForm`. Tuttavia, sebbene `anyForm` può accedere a tutti i membri della classe <xref:System.Windows.Forms.Form>, non può usare uno dei metodi aggiuntivi o le proprietà definite per i moduli specifici, ad esempio `specialForm`.  
  
 Tutti i membri di una classe base sono disponibili per le classi derivate, ma i membri aggiuntivi di una classe derivata non sono disponibili per la classe di base.  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Procedura: Dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Procedura: Accedere ai membri di un oggetto](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Operatore New](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
