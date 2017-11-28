---
title: Dichiarazione di variabili oggetto (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cdca188d778e9884f918d97eba492a29c64af826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-declaration-visual-basic"></a>Dichiarazione di variabili oggetto (Visual Basic)
Utilizzare una normale istruzione di dichiarazione per dichiarare una variabile oggetto. Per il tipo di dati, specificare `Object` (vale a dire il [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)) o una classe più specifica da cui è possibile creare l'oggetto.  
  
 Dichiarazione di una variabile come `Object` corrisponde alla dichiarazione come <xref:System.Object?displayProperty=nameWithType>.  
  
 Quando si dichiara una variabile con una classe di oggetto specifico, è possibile accedere a tutti i metodi e proprietà esposte da tale classe e le classi da cui eredita. Se si dichiara una variabile con <xref:System.Object>, può accedere solo i membri del <xref:System.Object> classe, a meno che non si attiva `Option Strict Off` per consentire l'associazione tardiva.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 Utilizzare la sintassi seguente per dichiarare una variabile oggetto:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 È inoltre possibile specificare [pubblica](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [privata](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), o [statico](../../../../visual-basic/language-reference/modifiers/static.md) nella dichiarazione. Le dichiarazioni di esempio seguenti sono valide:  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>L'associazione tardiva e l'associazione anticipata  
 In alcuni casi la classe specifica è sconosciuta fino a quando non viene eseguito il codice. In questo caso, è necessario dichiarare la variabile oggetto con il `Object` tipo di dati. Crea un riferimento generale a qualsiasi tipo di oggetto e la classe specifica viene assegnata in fase di esecuzione. Si tratta di *ad associazione tardiva*. L'associazione tardiva richiede più tempo di esecuzione. Limita anche il codice per i metodi e proprietà della classe che è stato assegnato più di recente a esso. Questo può causare errori di run-time se il codice tenta di accedere ai membri di un'altra classe.  
  
 Quando si conosce la classe specifica in fase di compilazione, è necessario dichiarare la variabile di oggetto di tale classe. Questa operazione è definita *associazione anticipata*. Associazione anticipata migliora le prestazioni e garantisce l'accesso di codice a tutti i metodi e proprietà della classe specifica. Nelle dichiarazioni di esempio precedente, se la variabile `objA` Usa solo gli oggetti della classe <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, è necessario specificare `As System.Windows.Forms.Label` nella relativa dichiarazione.  
  
### <a name="advantages-of-early-binding"></a>Vantaggi offerti dall'associazione anticipata  
 Dichiarare una variabile oggetto come una classe specifica offre diversi vantaggi:  
  
-   Controllo automatico del tipo  
  
-   È garantito l'accesso a tutti i membri della classe specifico  
  
-   Supporto Microsoft IntelliSense nell'Editor di codice  
  
-   Migliorare la leggibilità del codice  
  
-   Un minor numero di errori nel codice  
  
-   Rilevata degli errori in fase di compilazione anziché di runtime  
  
-   Esecuzione di codice più veloce  
  
## <a name="access-to-object-variable-members"></a>Accesso ai membri delle variabili oggetto  
 Quando `Option Strict` sia `On`, una variabile oggetto può accedere solo ai metodi e proprietà della classe con cui viene dichiarata. Questa condizione è illustrata nell'esempio seguente.  
  
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
 Quando si lavora con gli oggetti in una gerarchia di ereditarietà, si dispone di una scelta di quale classe usare per dichiarare le variabili oggetto. Effettuare questa scelta, è necessario bilanciare la flessibilità dell'assegnazione di oggetto e l'accesso ai membri di una classe. Si consideri ad esempio la gerarchia di ereditarietà che comporta la <xref:System.Windows.Forms.Form?displayProperty=nameWithType> classe:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Si supponga che l'applicazione definisce una classe del modulo chiamata `specialForm`, che eredita dalla classe <xref:System.Windows.Forms.Form>. È possibile dichiarare una variabile oggetto che fa riferimento in modo specifico a `specialForm`, come illustrato nell'esempio seguente.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 La dichiarazione nell'esempio precedente limita la variabile `nextForm` agli oggetti della classe `specialForm`, ma rende anche tutti i metodi e proprietà di `specialForm` disponibili per `nextForm`, nonché per tutti i membri di tutte le classi da cui `specialForm` eredita.  
  
 È possibile rendere una variabile oggetto più generale mediante la dichiarazione di tipo <xref:System.Windows.Forms.Form>, come illustrato nell'esempio seguente.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 La dichiarazione nell'esempio precedente consente di assegnare qualsiasi form nell'applicazione per `anyForm`. Tuttavia, anche se `anyForm` possono accedere tutti i membri della classe <xref:System.Windows.Forms.Form>, non può utilizzare uno dei metodi aggiuntivi o le proprietà definite per moduli specifici, ad esempio `specialForm`.  
  
 Tutti i membri di una classe di base sono disponibili per le classi derivate, ma i membri aggiuntivi di una classe derivata non sono disponibili per la classe di base.  
  
## <a name="see-also"></a>Vedere anche  
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [Procedura: accedere ai membri di un oggetto](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [Operatore New](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
