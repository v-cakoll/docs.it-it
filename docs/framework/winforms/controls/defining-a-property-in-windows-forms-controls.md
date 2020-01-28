---
title: Definire le proprietà del controllo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: 0fec817226a7da4b44ec992f9e384a2ad5449001
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746103"
---
# <a name="defining-a-property-in-windows-forms-controls"></a><span data-ttu-id="2d7e5-102">Definizione di una proprietà nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="2d7e5-102">Defining a Property in Windows Forms Controls</span></span>
<span data-ttu-id="2d7e5-103">Per una panoramica delle proprietà, vedere [Cenni preliminari sulle proprietà](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="2d7e5-103">For an overview of properties, see [Properties Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span></span> <span data-ttu-id="2d7e5-104">Quando si definisce una proprietà sono da considerare i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="2d7e5-104">There are a few important considerations when defining a property:</span></span>  
  
- <span data-ttu-id="2d7e5-105">È necessario applicare attributi alle proprietà definite.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-105">You must apply attributes to the properties you define.</span></span> <span data-ttu-id="2d7e5-106">Gli attributi specificano l'aspetto di una proprietà in una progettazione.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-106">Attributes specify how the designer should display a property.</span></span> <span data-ttu-id="2d7e5-107">Per informazioni dettagliate, vedere [Attributi per componenti in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="2d7e5-107">For details, see [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>  
  
- <span data-ttu-id="2d7e5-108">Se la modifica della proprietà influiscono sulla visualizzazione del controllo, chiamare il metodo <xref:System.Windows.Forms.Control.Invalidate%2A> (che il controllo eredita da <xref:System.Windows.Forms.Control>) dalla funzione di accesso `set`.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-108">If changing the property affects the visual display of the control, call the <xref:System.Windows.Forms.Control.Invalidate%2A> method (that your control inherits from <xref:System.Windows.Forms.Control>) from the `set` accessor.</span></span> <span data-ttu-id="2d7e5-109"><xref:System.Windows.Forms.Control.Invalidate%2A> chiama a sua volta il metodo <xref:System.Windows.Forms.Control.OnPaint%2A>, che consente di ricreare il controllo.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-109"><xref:System.Windows.Forms.Control.Invalidate%2A> in turn calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which redraws the control.</span></span> <span data-ttu-id="2d7e5-110">Più chiamate a <xref:System.Windows.Forms.Control.Invalidate%2A> comportano una singola chiamata al <xref:System.Windows.Forms.Control.OnPaint%2A> per garantire l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-110">Multiple calls to <xref:System.Windows.Forms.Control.Invalidate%2A> result in a single call to <xref:System.Windows.Forms.Control.OnPaint%2A> for efficiency.</span></span>  
  
- <span data-ttu-id="2d7e5-111">La libreria di classi .NET Framework fornisce convertitori di tipi per tipi di dati comuni, ad esempio numeri interi, numeri decimali, valori booleani e altri.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-111">The .NET Framework class library provides type converters for common data types such as integers, decimal numbers, Boolean values, and others.</span></span> <span data-ttu-id="2d7e5-112">Lo scopo di un convertitore di tipi è in genere quello di fornire la conversione da stringa a valore (da dati stringa in altri tipi di dati).</span><span class="sxs-lookup"><span data-stu-id="2d7e5-112">The purpose of a type converter is generally to provide string-to-value conversion (from string data to other data types).</span></span> <span data-ttu-id="2d7e5-113">I tipi di dati comuni sono associati a convertitori di tipi predefiniti che convertono i valori in stringhe e le stringhe in tipi di dati appropriati.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-113">Common data types are associated with default type converters that convert values into strings and strings into the appropriate data types.</span></span> <span data-ttu-id="2d7e5-114">Se si definisce una proprietà che è un tipo di dati personalizzati (vale a dire non standard), è necessario applicare un attributo che specifica il convertitore di tipi da associare a tale proprietà.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-114">If you define a property that is a custom (that is, nonstandard) data type, you will have to apply an attribute that specifies the type converter to associate with that property.</span></span> <span data-ttu-id="2d7e5-115">È inoltre possibile usare un attributo per associare un editor di tipi dell'interfaccia utente personalizzato a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-115">You can also use an attribute to associate a custom UI type editor with a property.</span></span> <span data-ttu-id="2d7e5-116">Un editor di tipi dell'interfaccia utente fornisce un'interfaccia utente per la modifica di un tipo di dati o proprietà.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-116">A UI type editor provides a user interface for editing a property or data type.</span></span> <span data-ttu-id="2d7e5-117">La selezione colori è un esempio di un editor di tipi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-117">A color picker is an example of a UI type editor.</span></span> <span data-ttu-id="2d7e5-118">Alla fine di questo argomento vengono forniti esempi di attributi.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-118">Examples of attributes are given at the end of this topic.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2d7e5-119">Se un convertitore di tipi o un editor di tipi dell'interfaccia utente non è disponibile per la proprietà personalizzata, è possibile implementarne uno come descritto in [Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="2d7e5-119">If a type converter or a UI type editor is not available for your custom property, you can implement one as described in [Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>  
  
 <span data-ttu-id="2d7e5-120">Il frammento di codice seguente definisce una proprietà personalizzata, chiamata `EndColor`, per il controllo personalizzato `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-120">The following code fragment defines a custom property named `EndColor` for the custom control `FlashTrackBar`.</span></span>  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.   
   ' The Description attribute provides a description of  
   ' the property.   
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws    
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.   
   // The Description attribute provides a description of  
   // the property.   
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws   
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 <span data-ttu-id="2d7e5-121">Nel frammento di codice seguente, un convertitore di tipi viene associato a un editor di tipi dell'interfaccia utente con la proprietà `Value`.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-121">The following code fragment associates a type converter and a UI type editor with the property `Value`.</span></span> <span data-ttu-id="2d7e5-122">In questo caso `Value` è un numero intero e ha un convertitore di tipi predefinito, ma l'attributo <xref:System.ComponentModel.TypeConverterAttribute> applica un convertitore di tipi personalizzato (`FlashTrackBarValueConverter`) che consente alla finestra di progettazione di visualizzarlo come percentuale.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-122">In this case `Value` is an integer and has a default type converter, but the <xref:System.ComponentModel.TypeConverterAttribute> attribute applies a custom type converter (`FlashTrackBarValueConverter`) that enables the designer to display it as a percentage.</span></span> <span data-ttu-id="2d7e5-123">L'editor di tipi dell'interfaccia utente, `FlashTrackBarValueEditor`, consente di rappresentare visivamente la percentuale.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-123">The UI type editor, `FlashTrackBarValueEditor`, allows the percentage to be displayed visually.</span></span> <span data-ttu-id="2d7e5-124">Questo esempio mostra anche che il convertitore di tipi o l'editor specificato dall'attributo <xref:System.ComponentModel.TypeConverterAttribute> o <xref:System.ComponentModel.EditorAttribute> esegue l'override del convertitore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2d7e5-124">This example also shows that the type converter or editor specified by the <xref:System.ComponentModel.TypeConverterAttribute> or <xref:System.ComponentModel.EditorAttribute> attribute overrides the default converter.</span></span>  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
```  
  
```csharp  
[  
Category("Flash"),   
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d7e5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d7e5-125">See also</span></span>

- [<span data-ttu-id="2d7e5-126">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="2d7e5-126">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="2d7e5-127">Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset</span><span class="sxs-lookup"><span data-stu-id="2d7e5-127">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [<span data-ttu-id="2d7e5-128">Eventi di modifica delle proprietà</span><span class="sxs-lookup"><span data-stu-id="2d7e5-128">Property-Changed Events</span></span>](property-changed-events.md)
- [<span data-ttu-id="2d7e5-129">Attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="2d7e5-129">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
