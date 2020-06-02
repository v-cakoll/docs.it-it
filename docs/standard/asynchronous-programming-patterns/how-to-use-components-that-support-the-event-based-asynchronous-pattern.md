---
title: 'Procedura: usare componenti che supportano il modello asincrono basato su eventi'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 0f15cd870efbdcd00dafa071175be078311a9a37
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289395"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Procedura: usare componenti che supportano il modello asincrono basato su eventi
Molti componenti consentono di eseguire le attività in modo asincrono. I componenti <xref:System.Media.SoundPlayer> e <xref:System.Windows.Forms.PictureBox>, ad esempio, consentono di caricare suoni e immagini "in background", mentre l'esecuzione del thread principale procede senza interruzioni.  
  
 L'uso di metodi asincroni in una classe che supporta il [modello asincrono basato su eventi](event-based-asynchronous-pattern-overview.md) può essere semplice quanto collegare un gestore eventi all'evento _MethodName_**Completed** del componente, come per qualsiasi altro evento. Quando si chiama il metodo _MethodName_**Async**, l'esecuzione dell'applicazione continua senza interruzioni fino alla generazione dell'evento _MethodName_**Completed**. Nel gestore eventi è possibile esaminare il parametro <xref:System.ComponentModel.AsyncCompletedEventArgs> per determinare se l'operazione asincrona è stata completata o se è stata annullata.  
  
 Per altre informazioni sull'uso dei gestori eventi, vedere [Cenni preliminari sui gestori eventi](../../framework/winforms/event-handlers-overview-windows-forms.md).  
  
 La procedura seguente mostra come usare la funzionalità asincrona di caricamento di immagini di un controllo <xref:System.Windows.Forms.PictureBox>.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Per abilitare un controllo PictureBox per caricare in modo asincrono un'immagine  
  
1. Creare un'istanza del componente <xref:System.Windows.Forms.PictureBox> nel modulo.  
  
2. Assegnare un gestore per l'evento <xref:System.Windows.Forms.PictureBox.LoadCompleted>.  
  
     Controllare gli eventuali errori che si sono verificati durante il download asincrono. Controllare anche l'eventuale annullamento.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3. Aggiungere due pulsanti, denominati `loadButton` e `cancelLoadButton`, nel modulo. Aggiungere gestori dell'evento <xref:System.Windows.Forms.Control.Click> per avviare e annullare il download.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4. Eseguire l'applicazione.  
  
     Man mano che il download dell'immagine procede, è possibile spostare liberamente il modulo, ridurlo e ingrandirlo.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Eseguire un'operazione in background](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Cenni preliminari sul modello asincrono basato su eventi](event-based-asynchronous-pattern-overview.md)
