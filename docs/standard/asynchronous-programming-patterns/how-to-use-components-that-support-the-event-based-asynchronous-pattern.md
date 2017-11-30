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
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="a48a2-102">Procedura: usare componenti che supportano il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="a48a2-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="a48a2-103">Molti componenti offrono la possibilità di eseguire le attività in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="a48a2-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="a48a2-104">Il <xref:System.Media.SoundPlayer> e <xref:System.Windows.Forms.PictureBox> componenti, ad esempio, consentono di caricare suoni e immagini "in background", mentre l'esecuzione del thread principale procede senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="a48a2-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="a48a2-105">Utilizzare i metodi asincroni in una classe che supporta il [Panoramica del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) può essere semplice come associare un gestore eventi per il componente *NomeMetodo* `Completed` evento, Analogamente a come si farebbe per qualsiasi altro evento.</span><span class="sxs-lookup"><span data-stu-id="a48a2-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's *MethodName*`Completed` event, just as you would for any other event.</span></span> <span data-ttu-id="a48a2-106">Quando si chiama il *NomeMetodo* `Async` (metodo), l'applicazione continua l'esecuzione senza interruzione fino a quando il *NomeMetodo* `Completed` viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="a48a2-106">When you call the *MethodName*`Async` method, your application will continue running without interruption until the *MethodName*`Completed` event is raised.</span></span> <span data-ttu-id="a48a2-107">Nel gestore eventi, è possibile esaminare il <xref:System.ComponentModel.AsyncCompletedEventArgs> parametro per determinare se l'operazione asincrona è stata completata o se è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="a48a2-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="a48a2-108">Per ulteriori informazioni sull'utilizzo di gestori eventi, vedere [panoramica dei gestori eventi](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a48a2-108">For more information about using event handlers, see [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="a48a2-109">La procedura seguente viene illustrato come utilizzare la funzionalità asincrona di caricamento dell'immagine di un <xref:System.Windows.Forms.PictureBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="a48a2-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="a48a2-110">Per attivare un controllo PictureBox caricare in modo asincrono un'immagine</span><span class="sxs-lookup"><span data-stu-id="a48a2-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1.  <span data-ttu-id="a48a2-111">Creare un'istanza di <xref:System.Windows.Forms.PictureBox> componente nel form.</span><span class="sxs-lookup"><span data-stu-id="a48a2-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2.  <span data-ttu-id="a48a2-112">Assegnare un gestore eventi per il <xref:System.Windows.Forms.PictureBox.LoadCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="a48a2-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="a48a2-113">Controllare gli eventuali errori verificatisi durante il download asincrono qui.</span><span class="sxs-lookup"><span data-stu-id="a48a2-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="a48a2-114">È anche in cui verificare la disponibilità di annullamento.</span><span class="sxs-lookup"><span data-stu-id="a48a2-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  <span data-ttu-id="a48a2-115">Aggiungere due pulsanti, denominati `loadButton` e `cancelLoadButton`, al form.</span><span class="sxs-lookup"><span data-stu-id="a48a2-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="a48a2-116">Aggiungere <xref:System.Windows.Forms.Control.Click> gestori di eventi di avvio e annullamento del download.</span><span class="sxs-lookup"><span data-stu-id="a48a2-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="a48a2-117">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a48a2-117">Run your application.</span></span>  
  
     <span data-ttu-id="a48a2-118">Durante il download dell'immagine, è possibile spostare liberamente il form, ridurre e ingrandirla.</span><span class="sxs-lookup"><span data-stu-id="a48a2-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48a2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a48a2-119">See Also</span></span>  
 [<span data-ttu-id="a48a2-120">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="a48a2-120">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="a48a2-121">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="a48a2-121">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="a48a2-122">NOT IN BUILD: Multithreading in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a48a2-122">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
