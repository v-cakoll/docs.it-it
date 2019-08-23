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
ms.openlocfilehash: 609fe4896a2b01b8a69ff8a3d0854c85ddbd6a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969089"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset
`ShouldSerialize`e `Reset` sono metodi facoltativi che è possibile fornire per una proprietà, se la proprietà non dispone di un valore predefinito semplice. Se la proprietà ha un valore predefinito semplice, è necessario applicare <xref:System.ComponentModel.DefaultValueAttribute> e fornire il valore predefinito al costruttore della classe Attribute. Uno di questi meccanismi Abilita le funzionalità seguenti nella finestra di progettazione:

- La proprietà fornisce un'indicazione visiva nel Visualizzatore proprietà se è stata modificata rispetto al valore predefinito.

- L'utente può fare clic con il pulsante destro del mouse sulla proprietà e scegliere **Reimposta** per ripristinare il valore predefinito della proprietà.

- La finestra di progettazione genera codice più efficiente.

    > [!NOTE]
    > Applicare o fornire <xref:System.ComponentModel.DefaultValueAttribute> `Reset`i metodi *PropertyName* e `ShouldSerialize` *PropertyName* . Non usare entrambi.

 Il `Reset`metodo *PropertyName* imposta una proprietà sul relativo valore predefinito, come illustrato nel frammento di codice seguente.

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
> Se una proprietà non dispone di un `Reset` metodo, non è contrassegnata con <xref:System.ComponentModel.DefaultValueAttribute>un oggetto e non dispone di un valore predefinito specificato nella relativa dichiarazione, `Reset` l'opzione per tale proprietà è disabilitata nel menu di scelta rapida della finestra **Proprietà** di Progettazione Windows Form in Visual Studio.

 Le finestre di progettazione, ad esempio `ShouldSerialize`Visual Studio, usano il metodo *PropertyName* per verificare se una proprietà è cambiata rispetto al valore predefinito e scrivere codice nel form solo se una proprietà viene modificata, consentendo così una generazione di codice più efficiente. Ad esempio:

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

 Di seguito è riportato un esempio di codice completo.

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

 In questo caso, anche quando il valore della variabile privata a cui si accede `MyFont` tramite la `null`proprietà è, il Visualizzatore proprietà non `null`viene visualizzato; in caso contrario <xref:System.Windows.Forms.Control.Font%2A> , Visualizza la proprietà dell'elemento padre, in `null`caso contrario. o il valore <xref:System.Windows.Forms.Control.Font%2A> predefinito definito in <xref:System.Windows.Forms.Control>. Pertanto, il valore predefinito `MyFont` di non può essere semplicemente impostato e <xref:System.ComponentModel.DefaultValueAttribute> non è possibile applicare un oggetto a questa proprietà. Al contrario, `ShouldSerialize` è `Reset` necessario implementare i metodi e per `MyFont` la proprietà.

## <a name="see-also"></a>Vedere anche

- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Definizione di una proprietà](defining-a-property-in-windows-forms-controls.md)
- [Eventi di modifica delle proprietà](property-changed-events.md)
