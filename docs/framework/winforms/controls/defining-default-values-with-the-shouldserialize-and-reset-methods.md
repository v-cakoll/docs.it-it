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
ms.openlocfilehash: 11181bacdb919693ffc82c48c061357463a6343b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336756"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset
`ShouldSerialize` e `Reset` sono metodi facoltativi che è possibile fornire per una proprietà, se la proprietà non dispone di un valore predefinito semplice. Se la proprietà ha un valore predefinito semplice, applicare il <xref:System.ComponentModel.DefaultValueAttribute> e fornire il valore predefinito al costruttore della classe Attribute. Uno di questi meccanismi Abilita le funzionalità seguenti nella finestra di progettazione:

- La proprietà fornisce un'indicazione visiva nel Visualizzatore proprietà se è stata modificata rispetto al valore predefinito.

- L'utente può fare clic con il pulsante destro del mouse sulla proprietà e scegliere **Reimposta** per ripristinare il valore predefinito della proprietà.

- La finestra di progettazione genera codice più efficiente.

    > [!NOTE]
    > Applicare il <xref:System.ComponentModel.DefaultValueAttribute> o fornire `Reset`metodi *PropertyName* e `ShouldSerialize`*PropertyName* . Non usare entrambi.

 Il metodo `Reset`*PropertyName* imposta una proprietà sul relativo valore predefinito, come illustrato nel frammento di codice seguente.

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
> Se una proprietà non ha un metodo di `Reset`, non è contrassegnata con un <xref:System.ComponentModel.DefaultValueAttribute>e non ha un valore predefinito specificato nella relativa dichiarazione, l'opzione `Reset` per tale proprietà è disabilitata nel menu di scelta rapida della finestra **Proprietà** del progettazione Windows Form in Visual Studio.

 Le finestre di progettazione quali Visual Studio usano il metodo `ShouldSerialize`*PropertyName* per verificare se una proprietà è cambiata rispetto al valore predefinito e scrivere codice nel form solo se una proprietà viene modificata, consentendo così una generazione di codice più efficiente. Di seguito è riportato un esempio:

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

Imports System.Drawing
Imports System.Windows.Forms

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
using System.Drawing;
using System.Windows.Forms;

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

 In questo caso, anche quando il valore della variabile privata a cui si accede tramite la proprietà `MyFont` è `null`, il Visualizzatore proprietà non visualizza `null`; viene invece visualizzata la proprietà <xref:System.Windows.Forms.Control.Font%2A> dell'elemento padre, se non è `null`, oppure il valore predefinito del <xref:System.Windows.Forms.Control.Font%2A> definito in <xref:System.Windows.Forms.Control>. Pertanto non è possibile impostare semplicemente il valore predefinito per `MyFont` e non è possibile applicare una <xref:System.ComponentModel.DefaultValueAttribute> a questa proprietà. Al contrario, è necessario implementare i metodi `ShouldSerialize` e `Reset` per la proprietà `MyFont`.

## <a name="see-also"></a>Vedere anche

- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Definizione di una proprietà](defining-a-property-in-windows-forms-controls.md)
- [Eventi di modifica delle proprietà](property-changed-events.md)
