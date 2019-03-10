---
title: Cenni preliminari sui gestori eventi (Windows Form)
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
ms.openlocfilehash: 6dbcffadfd484dc33db2fcd3ee3f680dcc0740e5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703387"
---
# <a name="event-handlers-overview-windows-forms"></a>Cenni preliminari sui gestori eventi (Windows Form)
Un gestore eventi è un metodo che è associato a un evento. Quando viene generato l'evento, viene eseguito il codice nel gestore eventi. Ogni gestore di evento fornisce due parametri che consentono di gestire correttamente l'evento. Nell'esempio seguente viene illustrato un gestore eventi per un <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> evento.  
  
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
  
 Il primo parametro,`sender`, fornisce un riferimento all'oggetto che ha generato l'evento. Il secondo parametro, `e`, nell'esempio precedente, passa un oggetto specifico per l'evento che viene gestito. Facendo riferimento alle proprietà dell'oggetto (e, in alcuni casi, i relativi metodi), è possibile ottenere informazioni quali la posizione del mouse per eventi del mouse o dati trasferiti negli eventi di trascinamento e rilascio.  
  
 In genere ogni evento produce un gestore eventi con un tipo di evento a un oggetto diverso per il secondo parametro. Alcuni gestori di eventi, ad esempio quelli per il <xref:System.Windows.Forms.Control.MouseDown> e <xref:System.Windows.Forms.Control.MouseUp> eventi, hanno lo stesso tipo di oggetto per il secondo parametro. Per questi tipi di eventi, è possibile usare lo stesso gestore eventi per gestire entrambi gli eventi.  
  
 È anche possibile usare lo stesso gestore eventi per gestire l'evento stesso per diversi controlli. Ad esempio, se si dispone di un gruppo di <xref:System.Windows.Forms.RadioButton> controlli in un form, è possibile creare un unico gestore eventi per il <xref:System.Windows.Forms.Control.Click> evento e ogni controllo <xref:System.Windows.Forms.Control.Click> eventi associati al gestore di evento singolo. Per altre informazioni, vedere [Procedura: Connettere più eventi a un unico gestore eventi in Windows Form](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche
- [Creazione di gestori eventi in Windows Form](creating-event-handlers-in-windows-forms.md)
- [Informazioni generali sugli eventi](events-overview-windows-forms.md)
