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
ms.openlocfilehash: 9ac98b5c576c065f8944714c72b492539e0d2f05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "61870240"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="74053-102">Procedura: usare componenti che supportano il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="74053-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="74053-103">Molti componenti consentono di eseguire le attività in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="74053-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="74053-104">I componenti <xref:System.Media.SoundPlayer> e <xref:System.Windows.Forms.PictureBox>, ad esempio, consentono di caricare suoni e immagini "in background", mentre l'esecuzione del thread principale procede senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="74053-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="74053-105">L'uso di metodi asincroni in una classe che supporta il [modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) può essere semplice quanto collegare un gestore eventi all'evento _MethodName_**Completed** del componente, come per qualsiasi altro evento.</span><span class="sxs-lookup"><span data-stu-id="74053-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's _MethodName_**Completed** event, just as you would for any other event.</span></span> <span data-ttu-id="74053-106">Quando si chiama il metodo _MethodName_**Async**, l'esecuzione dell'applicazione continua senza interruzioni fino alla generazione dell'evento _MethodName_**Completed**.</span><span class="sxs-lookup"><span data-stu-id="74053-106">When you call the _MethodName_**Async** method, your application will continue running without interruption until the _MethodName_**Completed** event is raised.</span></span> <span data-ttu-id="74053-107">Nel gestore eventi è possibile esaminare il parametro <xref:System.ComponentModel.AsyncCompletedEventArgs> per determinare se l'operazione asincrona è stata completata o se è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="74053-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="74053-108">Per altre informazioni sull'uso dei gestori eventi, vedere [Cenni preliminari sui gestori eventi](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="74053-108">For more information about using event handlers, see [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="74053-109">La procedura seguente mostra come usare la funzionalità asincrona di caricamento di immagini di un controllo <xref:System.Windows.Forms.PictureBox>.</span><span class="sxs-lookup"><span data-stu-id="74053-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="74053-110">Per abilitare un controllo PictureBox per caricare in modo asincrono un'immagine</span><span class="sxs-lookup"><span data-stu-id="74053-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1. <span data-ttu-id="74053-111">Creare un'istanza del componente <xref:System.Windows.Forms.PictureBox> nel modulo.</span><span class="sxs-lookup"><span data-stu-id="74053-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2. <span data-ttu-id="74053-112">Assegnare un gestore per l'evento <xref:System.Windows.Forms.PictureBox.LoadCompleted>.</span><span class="sxs-lookup"><span data-stu-id="74053-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="74053-113">Controllare gli eventuali errori che si sono verificati durante il download asincrono.</span><span class="sxs-lookup"><span data-stu-id="74053-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="74053-114">Controllare anche l'eventuale annullamento.</span><span class="sxs-lookup"><span data-stu-id="74053-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3. <span data-ttu-id="74053-115">Aggiungere due pulsanti, denominati `loadButton` e `cancelLoadButton`, nel modulo.</span><span class="sxs-lookup"><span data-stu-id="74053-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="74053-116">Aggiungere gestori dell'evento <xref:System.Windows.Forms.Control.Click> per avviare e annullare il download.</span><span class="sxs-lookup"><span data-stu-id="74053-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4. <span data-ttu-id="74053-117">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74053-117">Run your application.</span></span>  
  
     <span data-ttu-id="74053-118">Man mano che il download dell'immagine procede, è possibile spostare liberamente il modulo, ridurlo e ingrandirlo.</span><span class="sxs-lookup"><span data-stu-id="74053-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74053-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74053-119">See also</span></span>

- [<span data-ttu-id="74053-120">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="74053-120">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="74053-121">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="74053-121">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
