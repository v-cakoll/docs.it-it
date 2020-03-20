---
title: Panoramica sui gestori eventi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141692"
---
# <a name="event-handlers-overview-windows-forms"></a>Cenni preliminari sui gestori eventi (Windows Form)
Un gestore eventi è un metodo associato a un evento. Quando viene generato l'evento, viene eseguito il codice all'interno del gestore eventi. Ogni gestore eventi fornisce due parametri che consentono di gestire correttamente l'evento. Nell'esempio seguente viene illustrato <xref:System.Windows.Forms.Button> un <xref:System.Windows.Forms.Control.Click> gestore eventi per l'evento di un controllo.  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 Il primo`sender`parametro, , fornisce un riferimento all'oggetto che ha generato l'evento. Il secondo `e`parametro, , nell'esempio precedente, passa un oggetto specifico all'evento che viene gestito. Facendo riferimento alle proprietà dell'oggetto (e, talvolta, ai relativi metodi), è possibile ottenere informazioni quali la posizione del mouse per gli eventi del mouse o i dati trasferiti negli eventi di trascinamento della selezione.  
  
 In genere ogni evento produce un gestore eventi con un tipo di oggetto-evento diverso per il secondo parametro. Alcuni gestori eventi, ad <xref:System.Windows.Forms.Control.MouseDown> esempio <xref:System.Windows.Forms.Control.MouseUp> quelli per gli eventi e , hanno lo stesso tipo di oggetto per il secondo parametro. Per questi tipi di eventi, è possibile usare lo stesso gestore eventi per gestire entrambi gli eventi.  
  
 È inoltre possibile utilizzare lo stesso gestore eventi per gestire lo stesso evento per controlli diversi. Ad esempio, se si <xref:System.Windows.Forms.RadioButton> dispone di un gruppo di controlli in <xref:System.Windows.Forms.Control.Click> un form, è <xref:System.Windows.Forms.Control.Click> possibile creare un singolo gestore eventi per l'evento e associare l'evento di ogni controllo al singolo gestore eventi. Per ulteriori informazioni, vedere [Procedura: connettere più eventi a un singolo gestore eventi in Windows Form](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di gestori eventi in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Cenni preliminari sugli eventi](events-overview-windows-forms.md)
