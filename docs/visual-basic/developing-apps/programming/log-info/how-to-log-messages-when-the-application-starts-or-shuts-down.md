---
title: "Procedura: Registrare messaggi all'avvio o all'arresto dell'applicazione"
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event [Visual Basic]
- event logs, startup
- Shutdown event [Visual Basic]
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
ms.openlocfilehash: 5a4ef3888ba8371d26204c3569b5fb9bae1f15f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352104"
---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a><span data-ttu-id="ca1ee-102">Procedura: registrare messaggi all'avvio o all'arresto dell'applicazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca1ee-102">How to: Log Messages When the Application Starts or Shuts Down (Visual Basic)</span></span>

<span data-ttu-id="ca1ee-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sugli eventi che si verificano nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="ca1ee-104">Questo esempio illustra come usare il metodo `My.Application.Log.WriteEntry` con gli eventi `Startup` e `Shutdown` per scrivere informazioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-104">This example shows how to use the `My.Application.Log.WriteEntry` method with the `Startup` and `Shutdown` events to write tracing information.</span></span>  
  
### <a name="to-access-the-applications-event-handler-code"></a><span data-ttu-id="ca1ee-105">Per accedere al codice del gestore eventi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ca1ee-105">To access the application's event-handler code</span></span>  
  
1. <span data-ttu-id="ca1ee-106">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-106">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ca1ee-107">Scegliere **Proprietà**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="ca1ee-107">On the **Project** menu, choose **Properties**.</span></span>  
  
2. <span data-ttu-id="ca1ee-108">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="ca1ee-108">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="ca1ee-109">Fare clic sul pulsante **Visualizza eventi applicazione** per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-109">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="ca1ee-110">Verrà aperto il file ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-110">This opens the ApplicationEvents.vb file.</span></span>  
  
### <a name="to-log-messages-when-the-application-starts"></a><span data-ttu-id="ca1ee-111">Per registrare messaggi all'avvio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ca1ee-111">To log messages when the application starts</span></span>  
  
1. <span data-ttu-id="ca1ee-112">Aprire il file ApplicationEvents.vb nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-112">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="ca1ee-113">Scegliere **Eventi MyApplication** dal menu **Generale**.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-113">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2. <span data-ttu-id="ca1ee-114">Scegliere **Avvio** dal menu **Dichiarazioni**.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-114">On the **Declarations** menu, choose **Startup**.</span></span>  
  
     <span data-ttu-id="ca1ee-115">L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> prima dell'esecuzione dell'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-115">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> event before the main application runs.</span></span>  
  
3. <span data-ttu-id="ca1ee-116">Aggiungere il metodo `My.Application.Log.WriteEntry` al gestore eventi `Startup` .</span><span class="sxs-lookup"><span data-stu-id="ca1ee-116">Add the `My.Application.Log.WriteEntry` method to the `Startup` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#1)]  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a><span data-ttu-id="ca1ee-117">Per registrare messaggi all'arresto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ca1ee-117">To log messages when the application shuts down</span></span>  
  
1. <span data-ttu-id="ca1ee-118">Aprire il file ApplicationEvents.vb nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-118">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="ca1ee-119">Scegliere **Eventi MyApplication** dal menu **Generale**.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-119">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2. <span data-ttu-id="ca1ee-120">Scegliere **Arresto** dal menu **Dichiarazioni**.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-120">On the **Declarations** menu, choose **Shutdown**.</span></span>  
  
     <span data-ttu-id="ca1ee-121">L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> dopo l'esecuzione dell'applicazione principale, ma prima dell'arresto.</span><span class="sxs-lookup"><span data-stu-id="ca1ee-121">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> event after the main application runs, but before it shuts down.</span></span>  
  
3. <span data-ttu-id="ca1ee-122">Aggiungere il metodo `My.Application.Log.WriteEntry` al gestore eventi `Shutdown` .</span><span class="sxs-lookup"><span data-stu-id="ca1ee-122">Add the `My.Application.Log.WriteEntry` method to the `Shutdown` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="ca1ee-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca1ee-123">Example</span></span>  

 <span data-ttu-id="ca1ee-124">Per accedere agli eventi dell'applicazione nell'editor del codice è possibile usare **Creazione progetti** .</span><span class="sxs-lookup"><span data-stu-id="ca1ee-124">You can use the **Project Designer** to access the application events in the Code Editor.</span></span> <span data-ttu-id="ca1ee-125">Per altre informazioni, vedere [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ca1ee-125">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 [!code-vb[VbVbalrMyApplicationLog#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ca1ee-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ca1ee-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="ca1ee-127">Application Page, Project Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca1ee-127">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="ca1ee-128">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="ca1ee-128">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
