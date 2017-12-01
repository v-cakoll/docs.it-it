---
title: 'Procedura: usare componenti che supportano il modello asincrono basato su eventi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49e03a8d886ccd4ed6e4b2a19692c1874f5928ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Procedura: usare componenti che supportano il modello asincrono basato su eventi
Molti componenti offrono la possibilità di eseguire le attività in modo asincrono. Il <xref:System.Media.SoundPlayer> e <xref:System.Windows.Forms.PictureBox> componenti, ad esempio, consentono di caricare suoni e immagini "in background", mentre l'esecuzione del thread principale procede senza interruzioni.  
  
 Utilizzare i metodi asincroni in una classe che supporta il [Panoramica del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) può essere semplice come associare un gestore eventi per il componente *NomeMetodo* `Completed` evento, Analogamente a come si farebbe per qualsiasi altro evento. Quando si chiama il *NomeMetodo* `Async` (metodo), l'applicazione continua l'esecuzione senza interruzione fino a quando il *NomeMetodo* `Completed` viene generato l'evento. Nel gestore eventi, è possibile esaminare il <xref:System.ComponentModel.AsyncCompletedEventArgs> parametro per determinare se l'operazione asincrona è stata completata o se è stata annullata.  
  
 Per ulteriori informazioni sull'utilizzo di gestori eventi, vedere [panoramica dei gestori eventi](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 La procedura seguente viene illustrato come utilizzare la funzionalità asincrona di caricamento dell'immagine di un <xref:System.Windows.Forms.PictureBox> controllo.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Per attivare un controllo PictureBox caricare in modo asincrono un'immagine  
  
1.  Creare un'istanza di <xref:System.Windows.Forms.PictureBox> componente nel form.  
  
2.  Assegnare un gestore eventi per il <xref:System.Windows.Forms.PictureBox.LoadCompleted> evento.  
  
     Controllare gli eventuali errori verificatisi durante il download asincrono qui. È anche in cui verificare la disponibilità di annullamento.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Aggiungere due pulsanti, denominati `loadButton` e `cancelLoadButton`, al form. Aggiungere <xref:System.Windows.Forms.Control.Click> gestori di eventi di avvio e annullamento del download.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Eseguire l'applicazione.  
  
     Durante il download dell'immagine, è possibile spostare liberamente il form, ridurre e ingrandirla.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Eseguire un'operazione in background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
