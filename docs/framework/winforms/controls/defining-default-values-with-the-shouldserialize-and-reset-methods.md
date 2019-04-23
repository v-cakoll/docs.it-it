---
title: Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: f1f5a668c5d4f52ef7dd9f60a31c04f2173165f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090615"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset
`ShouldSerialize` e `Reset` sono metodi facoltativi che è possibile specificare per una proprietà, se la proprietà non presenta un valore predefinito semplice. Se la proprietà ha un valore predefinito semplice, è consigliabile applicare il <xref:System.ComponentModel.DefaultValueAttribute> e fornire invece il valore predefinito per il costruttore di classe di attributo. Uno di questi meccanismi Abilita le funzionalità seguenti nella finestra di progettazione:  
  
-   La proprietà fornisce un'indicazione visiva nel Visualizzatore proprietà se è stato modificato rispetto al valore predefinito.  
  
-   L'utente può fare doppio clic sulla proprietà e scegliere **reimpostare** per ripristinare la proprietà sul valore predefinito.  
  
-   La finestra di progettazione genera codice più efficiente.  
  
    > [!NOTE]
    >  Entrambi si applicano i <xref:System.ComponentModel.DefaultValueAttribute> o fornire `Reset` *PropertyName* e `ShouldSerialize` *PropertyName* metodi. Non utilizzare entrambi.  
  
 Il `Reset` *NomeProprietà* metodo imposta una proprietà sul valore predefinito, come illustrato nel frammento di codice seguente.  
  
```vb  
Public Sub ResetMyFont()  
   MyFont = Nothing  
End Sub  
```  
  
```csharp  
public void ResetMyFont() {  
   MyFont = null;  
}  
```  
  
> [!NOTE]
>  Se una proprietà non ha un `Reset` metodo, non è contrassegnato con un <xref:System.ComponentModel.DefaultValueAttribute>e non dispone di un valore predefinito fornito nella relativa dichiarazione, il `Reset` opzione per tale proprietà è disabilitata nel menu di scelta rapida del **proprietà** finestra di progettazione Windows Form in Visual Studio.  
  
 Finestre di progettazione, ad esempio Visual Studio usare il `ShouldSerialize` *NomeProprietà* metodo per verificare se una proprietà è stata modificata rispetto al valore predefinito e per scrivere codice nel form solo in una proprietà viene modificato, consentendo in tal modo per il codice più efficiente generazione. Ad esempio:  
  
```vb  
'Returns true if the font has changed; otherwise, returns false.  
' The designer writes code to the form only if true is returned.  
Public Function ShouldSerializeMyFont() As Boolean  
   Return Not (thefont Is Nothing)  
End Function  
```  
  
```csharp  
// Returns true if the font has changed; otherwise, returns false.  
// The designer writes code to the form only if true is returned.  
public bool ShouldSerializeMyFont() {  
   return thefont != null;  
}  
```  
  
 Segue un esempio di codice completo.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class MyControl  
   Inherits Control  
  
   ' Declare an instance of the Font class  
   ' and set its default value to Nothing.  
   Private thefont As Font = Nothing  
  
   ' The MyFont property.   
   Public Property MyFont() As Font  
      ' Note that the Font property never  
      ' returns null.  
      Get  
         If Not (thefont Is Nothing) Then  
            Return thefont  
         End If  
         If Not (Parent Is Nothing) Then  
            Return Parent.Font  
         End If  
         Return Control.DefaultFont  
      End Get  
      Set  
         thefont = value  
      End Set  
   End Property  
  
   Public Function ShouldSerializeMyFont() As Boolean  
      Return Not (thefont Is Nothing)  
   End Function  
  
   Public Sub ResetMyFont()  
      MyFont = Nothing  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class MyControl : Control {  
   // Declare an instance of the Font class  
   // and set its default value to null.  
   private Font thefont = null;  
  
   // The MyFont property.      
   public Font MyFont {  
      // Note that the MyFont property never  
      // returns null.  
      get {  
         if (thefont != null) return thefont;  
         if (Parent != null) return Parent.Font;  
         return Control.DefaultFont;  
      }  
      set {  
         thefont = value;  
      }  
   }  
  
   public bool ShouldSerializeMyFont() {  
      return thefont != null;  
   }  
  
   public void ResetMyFont() {  
      MyFont = null;  
   }  
}  
```  
  
 In questo caso, anche quando il valore della variabile privata accessibile dal `MyFont` proprietà è `null`, il Visualizzatore proprietà non viene visualizzata `null`; in alternativa, viene visualizzato il <xref:System.Windows.Forms.Control.Font%2A> proprietà dell'elemento padre, se non è `null`, o il valore predefinito <xref:System.Windows.Forms.Control.Font%2A> valore definito <xref:System.Windows.Forms.Control>. In questo modo il valore predefinito per `MyFont` non è possibile impostare semplicemente e un <xref:System.ComponentModel.DefaultValueAttribute> non può essere applicato a questa proprietà. Al contrario, il `ShouldSerialize` e `Reset` devono essere implementati i metodi per il `MyFont` proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Definizione di una proprietà](defining-a-property-in-windows-forms-controls.md)
- [Eventi di modifica delle proprietà](property-changed-events.md)
