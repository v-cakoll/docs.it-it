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
ms.openlocfilehash: a641b1e7565842a1edf6aeec88bdc37ee0786ab4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969121"
---
# <a name="defining-a-property-in-windows-forms-controls"></a>Definizione di una proprietà nei controlli Windows Form
Per una panoramica delle proprietà, vedere [Cenni preliminari sulle proprietà](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)). Quando si definisce una proprietà sono da considerare i seguenti elementi:  
  
- È necessario applicare attributi alle proprietà definite. Gli attributi specificano l'aspetto di una proprietà in una progettazione. Per informazioni dettagliate, vedere [Attributi per componenti in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).  
  
- Se la modifica della proprietà influisca sulla visualizzazione del controllo, chiamare il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo (da <xref:System.Windows.Forms.Control>cui il controllo eredita) dalla `set` funzione di accesso. <xref:System.Windows.Forms.Control.Invalidate%2A>chiama a sua volta <xref:System.Windows.Forms.Control.OnPaint%2A> il metodo, che consente di ricreare il controllo. Più chiamate a <xref:System.Windows.Forms.Control.Invalidate%2A> hanno come risultato una singola chiamata <xref:System.Windows.Forms.Control.OnPaint%2A> a per l'efficienza.  
  
- La libreria di classi .NET Framework fornisce convertitori di tipi per tipi di dati comuni, ad esempio numeri interi, numeri decimali, valori booleani e altri. Lo scopo di un convertitore di tipi è in genere quello di fornire la conversione da stringa a valore (da dati stringa in altri tipi di dati). I tipi di dati comuni sono associati a convertitori di tipi predefiniti che convertono i valori in stringhe e le stringhe in tipi di dati appropriati. Se si definisce una proprietà che è un tipo di dati personalizzati (vale a dire non standard), è necessario applicare un attributo che specifica il convertitore di tipi da associare a tale proprietà. È inoltre possibile usare un attributo per associare un editor di tipi dell'interfaccia utente personalizzato a una proprietà. Un editor di tipi dell'interfaccia utente fornisce un'interfaccia utente per la modifica di un tipo di dati o proprietà. La selezione colori è un esempio di un editor di tipi dell'interfaccia utente. Alla fine di questo argomento vengono forniti esempi di attributi.  
  
    > [!NOTE]
    > Se un convertitore di tipi o un editor di tipi dell'interfaccia utente non è disponibile per la proprietà personalizzata, è possibile implementarne uno come descritto in [Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).  
  
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
  
 Nel frammento di codice seguente, un convertitore di tipi viene associato a un editor di tipi dell'interfaccia utente con la proprietà `Value`. In questo caso `Value` è un numero intero e ha un convertitore di tipi predefinito, <xref:System.ComponentModel.TypeConverterAttribute> ma l'attributo applica un convertitore di`FlashTrackBarValueConverter`tipi personalizzato () che consente alla finestra di progettazione di visualizzarlo come percentuale. L'editor di tipi dell'interfaccia utente, `FlashTrackBarValueEditor`, consente di rappresentare visivamente la percentuale. Questo esempio mostra inoltre che il convertitore di tipi o l'editor specificato <xref:System.ComponentModel.TypeConverterAttribute> dall' <xref:System.ComponentModel.EditorAttribute> attributo o esegue l'override del convertitore predefinito.  
  
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

- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [Eventi di modifica delle proprietà](property-changed-events.md)
- [Attributi nei controlli Windows Forms](attributes-in-windows-forms-controls.md)
