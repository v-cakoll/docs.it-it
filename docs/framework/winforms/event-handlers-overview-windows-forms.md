---
title: Cenni preliminari sui gestori eventi (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44d79fb9d6ca2712c470354999b4795408044166
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
 Il primo parametro,`sender`, fornisce un riferimento all'oggetto che ha generato l'evento. Il secondo parametro, `e`, nell'esempio precedente passa un oggetto specifico per l'evento che viene gestito. Facendo riferimento alle proprietà dell'oggetto (e, in alcuni casi, i metodi), è possibile ottenere informazioni quali il percorso del puntatore del mouse per gli eventi del mouse o i dati trasferiti negli eventi di trascinamento e rilascio.  
  
 In genere, ogni evento produce un gestore eventi con un tipo di oggetto evento diverso per il secondo parametro. Gestori di eventi, ad esempio quelle per il <xref:System.Windows.Forms.Control.MouseDown> e <xref:System.Windows.Forms.Control.MouseUp> gli eventi, hanno lo stesso tipo di oggetto per il secondo parametro. Per questi tipi di eventi, è possibile utilizzare lo stesso gestore eventi per gestire entrambi gli eventi.  
  
 È anche possibile utilizzare lo stesso gestore eventi per gestire lo stesso evento per diversi controlli. Ad esempio, se si dispone di un gruppo di <xref:System.Windows.Forms.RadioButton> controlli in un form, è possibile creare un unico gestore eventi per il <xref:System.Windows.Forms.Control.Click> evento e di ciascun controllo <xref:System.Windows.Forms.Control.Click> associato al gestore dell'evento singolo evento. Per ulteriori informazioni, vedere [procedura: connettere più eventi a un singolo gestore eventi in Windows Form](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di gestori eventi in Windows Form](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Informazioni generali sugli eventi](../../../docs/framework/winforms/events-overview-windows-forms.md)
