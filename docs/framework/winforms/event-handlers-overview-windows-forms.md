---
title: Cenni preliminari sui gestori eventi
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
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743467"
---
# <a name="event-handlers-overview-windows-forms"></a>Panoramica dei gestori eventi (Windows Form)
Un gestore eventi è un metodo associato a un evento. Quando viene generato l'evento, il codice all'interno del gestore eventi viene eseguito. Ogni gestore eventi fornisce due parametri che consentono di gestire correttamente l'evento. Nell'esempio seguente viene illustrato un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> di un controllo <xref:System.Windows.Forms.Button>.  
  
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
  
 Il primo parametro,`sender`, fornisce un riferimento all'oggetto che ha generato l'evento. Il secondo parametro, `e`nell'esempio precedente, passa un oggetto specifico dell'evento che viene gestito. Facendo riferimento alle proprietà dell'oggetto (e talvolta ai relativi metodi), è possibile ottenere informazioni come la posizione del mouse per gli eventi del mouse o i dati trasferiti negli eventi di trascinamento della selezione.  
  
 In genere, ogni evento produce un gestore eventi con un tipo di oggetto evento diverso per il secondo parametro. Alcuni gestori di eventi, ad esempio quelli per gli eventi <xref:System.Windows.Forms.Control.MouseDown> e <xref:System.Windows.Forms.Control.MouseUp>, hanno lo stesso tipo di oggetto per il secondo parametro. Per questi tipi di eventi, è possibile usare lo stesso gestore eventi per gestire entrambi gli eventi.  
  
 È anche possibile usare lo stesso gestore eventi per gestire lo stesso evento per controlli diversi. Se, ad esempio, si dispone di un gruppo di controlli <xref:System.Windows.Forms.RadioButton> in un form, è possibile creare un singolo gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> e fare in modo che ogni <xref:System.Windows.Forms.Control.Click> evento del controllo venga associato al singolo gestore dell'evento. Per altre informazioni, vedere [procedura: connettere più eventi a un singolo gestore eventi in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di gestori eventi in Windows Form](creating-event-handlers-in-windows-forms.md)
- [Informazioni generali sugli eventi](events-overview-windows-forms.md)
