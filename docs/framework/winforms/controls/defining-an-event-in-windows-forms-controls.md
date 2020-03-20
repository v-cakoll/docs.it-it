---
title: Definire un evento nei controlliDefine an event in controls
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: 6799b229de8e8eb49dd3b8bbaffe0d08a32b7208
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142290"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="8f561-102">Definizione di un evento nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="8f561-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="8f561-103">Per informazioni dettagliate sulla definizione di eventi personalizzati, vedere [Eventi](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f561-103">For details about defining custom events, see [Events](../../../standard/events/index.md).</span></span> <span data-ttu-id="8f561-104">Se si definisce un evento che non presenta dati associati, usare il tipo base per i dati dell'evento, <xref:System.EventArgs>, e usare <xref:System.EventHandler> come delegato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8f561-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="8f561-105">Tutto ciò che resta da fare `On`è definire un membro dell'evento e un metodo *EventName* protetto che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="8f561-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="8f561-106">Il frammento di codice seguente illustra come il controllo personalizzato `FlashTrackBar` definisce un evento personalizzato, `ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="8f561-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="8f561-107">Per il codice `FlashTrackBar` completo dell'esempio, vedere [procedura: creare un controllo Windows Form che mostra lo stato](how-to-create-a-windows-forms-control-that-shows-progress.md)di avanzamento .</span><span class="sxs-lookup"><span data-stu-id="8f561-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate
   ' as the event delegate.
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged
   ' event when the value has actually
   ' changed. Derived controls can override this method.
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually
   // changed. Derived controls can override this method.
   protected virtual void OnValueChanged(EventArgs e)
   {  
       ValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f561-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f561-108">See also</span></span>

- [<span data-ttu-id="8f561-109">Eventi dei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8f561-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="8f561-110">Events</span><span class="sxs-lookup"><span data-stu-id="8f561-110">Events</span></span>](../../../standard/events/index.md)
