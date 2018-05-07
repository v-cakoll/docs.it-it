---
title: Definizione di una proprietà nei controlli Windows Form
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: dc47d7152419d55b3e52aec70257e2b39e9aaca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="defining-a-property-in-windows-forms-controls"></a>Definizione di una proprietà nei controlli Windows Form
Per una panoramica delle proprietà, vedere [Cenni preliminari sulle proprietà](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52). Quando si definisce una proprietà sono da considerare i seguenti elementi:  
  
-   È necessario applicare attributi alle proprietà definite. Gli attributi specificano l'aspetto di una proprietà in una progettazione. Per informazioni dettagliate, vedere [Attributi per componenti in fase di progettazione](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).  
  
-   Se la modifica della proprietà ha effetto sulla visualizzazione del controllo, chiamare il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo (che il controllo eredita da <xref:System.Windows.Forms.Control>) dal `set` della funzione di accesso. <xref:System.Windows.Forms.Control.Invalidate%2A> a sua volta chiama il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo, che consente di ricreare il controllo. Più chiamate al metodo <xref:System.Windows.Forms.Control.Invalidate%2A> risultato in una singola chiamata a <xref:System.Windows.Forms.Control.OnPaint%2A> per migliorare l'efficienza.  
  
-   La libreria di classi .NET Framework fornisce convertitori di tipi per tipi di dati comuni, ad esempio numeri interi, numeri decimali, valori booleani e altri. Lo scopo di un convertitore di tipi è in genere quello di fornire la conversione da stringa a valore (da dati stringa in altri tipi di dati). I tipi di dati comuni sono associati a convertitori di tipi predefiniti che convertono i valori in stringhe e le stringhe in tipi di dati appropriati. Se si definisce una proprietà che è un tipo di dati personalizzati (vale a dire non standard), è necessario applicare un attributo che specifica il convertitore di tipi da associare a tale proprietà. È inoltre possibile usare un attributo per associare un editor di tipi dell'interfaccia utente personalizzato a una proprietà. Un editor di tipi dell'interfaccia utente fornisce un'interfaccia utente per la modifica di un tipo di dati o proprietà. La selezione colori è un esempio di un editor di tipi dell'interfaccia utente. Alla fine di questo argomento vengono forniti esempi di attributi.  
  
    > [!NOTE]
    >  Se un convertitore di tipi o un editor di tipi dell'interfaccia utente non è disponibile per la proprietà personalizzata, è possibile implementarne uno come descritto in [Estensione del supporto in fase di progettazione](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).  
  
 Il frammento di codice seguente definisce una proprietà personalizzata, chiamata `EndColor`, per il controllo personalizzato `FlashTrackBar`.  
  
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
  
 Nel frammento di codice seguente, un convertitore di tipi viene associato a un editor di tipi dell'interfaccia utente con la proprietà `Value`. In questo caso `Value` è di tipo integer e dispone di un convertitore di tipo predefinito, ma la <xref:System.ComponentModel.TypeConverterAttribute> attributo si applica un convertitore di tipi personalizzato (`FlashTrackBarValueConverter`) che consente la finestra di progettazione per visualizzarlo come percentuale. L'editor di tipi dell'interfaccia utente, `FlashTrackBarValueEditor`, consente di rappresentare visivamente la percentuale. In questo esempio viene inoltre mostrato che il convertitore di tipi o specificato dall'editor di <xref:System.ComponentModel.TypeConverterAttribute> o <xref:System.ComponentModel.EditorAttribute> attributo esegue l'override del convertitore predefinito.  
  
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
  
## <a name="see-also"></a>Vedere anche  
 [Proprietà dei controlli Windows Form](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 [Eventi di modifica delle proprietà](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 [Attributi nei controlli Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)
