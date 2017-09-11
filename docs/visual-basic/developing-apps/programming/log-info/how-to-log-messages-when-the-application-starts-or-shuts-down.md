---
title: 'Procedura: registrare messaggi all''avvio o all''arresto dell''applicazione (Visual Basic)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event
- event logs, startup
- Shutdown event
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fa5bf57ac5245e9363089b85607b7e6d1a00ba14
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a><span data-ttu-id="63628-102">Procedura: registrare messaggi all'avvio o all'arresto dell'applicazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63628-102">How to: Log Messages When the Application Starts or Shuts Down (Visual Basic)</span></span>
<span data-ttu-id="63628-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sugli eventi che si verificano nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="63628-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="63628-104">Questo esempio illustra come usare il metodo `My.Application.Log.WriteEntry` con gli eventi `Startup` e `Shutdown` per scrivere informazioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="63628-104">This example shows how to use the `My.Application.Log.WriteEntry` method with the `Startup` and `Shutdown` events to write tracing information.</span></span>  
  
### <a name="to-access-the-applications-event-handler-code"></a><span data-ttu-id="63628-105">Per accedere al codice del gestore eventi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="63628-105">To access the application's event-handler code</span></span>  
  
1.  <span data-ttu-id="63628-106">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="63628-106">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="63628-107">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="63628-107">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="63628-108">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="63628-108">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="63628-109">Fare clic sul pulsante **Visualizza eventi applicazione** per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="63628-109">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="63628-110">Verrà aperto il file ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="63628-110">This opens the ApplicationEvents.vb file.</span></span>  
  
### <a name="to-log-messages-when-the-application-starts"></a><span data-ttu-id="63628-111">Per registrare messaggi all'avvio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="63628-111">To log messages when the application starts</span></span>  
  
1.  <span data-ttu-id="63628-112">Aprire il file ApplicationEvents.vb nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="63628-112">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="63628-113">Scegliere **Eventi MyApplication** dal menu **Generale**.</span><span class="sxs-lookup"><span data-stu-id="63628-113">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2.  <span data-ttu-id="63628-114">Scegliere **Avvio** dal menu **Dichiarazioni**.</span><span class="sxs-lookup"><span data-stu-id="63628-114">On the **Declarations** menu, choose **Startup**.</span></span>  
  
     <span data-ttu-id="63628-115">L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> prima dell'esecuzione dell'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="63628-115">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> event before the main application runs.</span></span>  
  
3.  <span data-ttu-id="63628-116">Aggiungere il metodo `My.Application.Log.WriteEntry` al gestore eventi `Startup` .</span><span class="sxs-lookup"><span data-stu-id="63628-116">Add the `My.Application.Log.WriteEntry` method to the `Startup` event handler.</span></span>  
  
     <span data-ttu-id="63628-117">[!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="63628-117">[!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]</span></span>  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a><span data-ttu-id="63628-118">Per registrare messaggi all'arresto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="63628-118">To log messages when the application shuts down</span></span>  
  
1.  <span data-ttu-id="63628-119">Aprire il file ApplicationEvents.vb nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="63628-119">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="63628-120">Scegliere **Eventi MyApplication** dal menu **Generale**.</span><span class="sxs-lookup"><span data-stu-id="63628-120">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2.  <span data-ttu-id="63628-121">Scegliere **Arresto** dal menu **Dichiarazioni**.</span><span class="sxs-lookup"><span data-stu-id="63628-121">On the **Declarations** menu, choose **Shutdown**.</span></span>  
  
     <span data-ttu-id="63628-122">L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> dopo l'esecuzione dell'applicazione principale, ma prima dell'arresto.</span><span class="sxs-lookup"><span data-stu-id="63628-122">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> event after the main application runs, but before it shuts down.</span></span>  
  
3.  <span data-ttu-id="63628-123">Aggiungere il metodo `My.Application.Log.WriteEntry` al gestore eventi `Shutdown` .</span><span class="sxs-lookup"><span data-stu-id="63628-123">Add the `My.Application.Log.WriteEntry` method to the `Shutdown` event handler.</span></span>  
  
     <span data-ttu-id="63628-124">[!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="63628-124">[!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="63628-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="63628-125">Example</span></span>  
 <span data-ttu-id="63628-126">Per accedere agli eventi dell'applicazione nell'editor del codice è possibile usare **Creazione progetti** .</span><span class="sxs-lookup"><span data-stu-id="63628-126">You can use the **Project Designer** to access the application events in the Code Editor.</span></span> <span data-ttu-id="63628-127">Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="63628-127">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="63628-128">[!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="63628-128">[!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63628-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63628-129">See Also</span></span>  
 <span data-ttu-id="63628-130"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="63628-130"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="63628-131"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="63628-131"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="63628-132"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="63628-132"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="63628-133">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  (Pagina Applicazione, Creazione progetti (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="63628-133">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
 [<span data-ttu-id="63628-134">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="63628-134">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)

