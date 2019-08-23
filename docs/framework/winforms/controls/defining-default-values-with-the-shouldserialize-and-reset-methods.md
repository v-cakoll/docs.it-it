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
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="ce9d9-102">Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset</span><span class="sxs-lookup"><span data-stu-id="ce9d9-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="ce9d9-103">`ShouldSerialize`e `Reset` sono metodi facoltativi che è possibile fornire per una proprietà, se la proprietà non dispone di un valore predefinito semplice.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="ce9d9-104">Se la proprietà ha un valore predefinito semplice, è necessario applicare <xref:System.ComponentModel.DefaultValueAttribute> e fornire il valore predefinito al costruttore della classe Attribute.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="ce9d9-105">Uno di questi meccanismi Abilita le funzionalità seguenti nella finestra di progettazione:</span><span class="sxs-lookup"><span data-stu-id="ce9d9-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="ce9d9-106">La proprietà fornisce un'indicazione visiva nel Visualizzatore proprietà se è stata modificata rispetto al valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="ce9d9-107">L'utente può fare clic con il pulsante destro del mouse sulla proprietà e scegliere **Reimposta** per ripristinare il valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="ce9d9-108">La finestra di progettazione genera codice più efficiente.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce9d9-109">Applicare o fornire <xref:System.ComponentModel.DefaultValueAttribute> `Reset`i metodi *PropertyName* e `ShouldSerialize` *PropertyName* .</span><span class="sxs-lookup"><span data-stu-id="ce9d9-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="ce9d9-110">Non usare entrambi.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-110">Do not use both.</span></span>

 <span data-ttu-id="ce9d9-111">Il `Reset`metodo *PropertyName* imposta una proprietà sul relativo valore predefinito, come illustrato nel frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="ce9d9-112">Se una proprietà non dispone di un `Reset` metodo, non è contrassegnata con <xref:System.ComponentModel.DefaultValueAttribute>un oggetto e non dispone di un valore predefinito specificato nella relativa dichiarazione, `Reset` l'opzione per tale proprietà è disabilitata nel menu di scelta rapida della finestra **Proprietà** di Progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="ce9d9-113">Le finestre di progettazione, ad esempio `ShouldSerialize`Visual Studio, usano il metodo *PropertyName* per verificare se una proprietà è cambiata rispetto al valore predefinito e scrivere codice nel form solo se una proprietà viene modificata, consentendo così una generazione di codice più efficiente.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="ce9d9-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ce9d9-114">For example:</span></span>

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

 <span data-ttu-id="ce9d9-115">Di seguito è riportato un esempio di codice completo.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-115">A complete code example follows.</span></span>

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

 <span data-ttu-id="ce9d9-116">In questo caso, anche quando il valore della variabile privata a cui si accede `MyFont` tramite la `null`proprietà è, il Visualizzatore proprietà non `null`viene visualizzato; in caso contrario <xref:System.Windows.Forms.Control.Font%2A> , Visualizza la proprietà dell'elemento padre, in `null`caso contrario. o il valore <xref:System.Windows.Forms.Control.Font%2A> predefinito definito in <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="ce9d9-117">Pertanto, il valore predefinito `MyFont` di non può essere semplicemente impostato e <xref:System.ComponentModel.DefaultValueAttribute> non è possibile applicare un oggetto a questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="ce9d9-118">Al contrario, `ShouldSerialize` è `Reset` necessario implementare i metodi e per `MyFont` la proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce9d9-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce9d9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce9d9-119">See also</span></span>

- [<span data-ttu-id="ce9d9-120">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="ce9d9-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="ce9d9-121">Definizione di una proprietà</span><span class="sxs-lookup"><span data-stu-id="ce9d9-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="ce9d9-122">Eventi di modifica delle proprietà</span><span class="sxs-lookup"><span data-stu-id="ce9d9-122">Property-Changed Events</span></span>](property-changed-events.md)
