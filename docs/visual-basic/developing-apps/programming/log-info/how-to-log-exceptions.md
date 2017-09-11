---
title: 'Procedura: registrare eccezioni in Visual Basic'
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
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: adf2dc683a139d21f24379efc779d4510a2057eb
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="c77d6-102">Procedura: registrare eccezioni in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c77d6-102">How to: Log Exceptions in Visual Basic</span></span>
<span data-ttu-id="c77d6-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sulle eccezioni generate nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c77d6-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="c77d6-104">Questi esempi illustrano come usare il metodo `My.Application.Log.WriteException` per registrare le eccezioni rilevate in modo esplicito e quelle non gestite.</span><span class="sxs-lookup"><span data-stu-id="c77d6-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="c77d6-105">Per registrare le informazioni di traccia, usare il metodo `My.Application.Log.WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="c77d6-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="c77d6-106">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.</span><span class="sxs-lookup"><span data-stu-id="c77d6-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="c77d6-107">Per registrare un'eccezione gestita</span><span class="sxs-lookup"><span data-stu-id="c77d6-107">To log a handled exception</span></span>  
  
1.  <span data-ttu-id="c77d6-108">Creare il metodo che genererà le informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c77d6-108">Create the method that will generate the exception information.</span></span>  
  
     <span data-ttu-id="c77d6-109">[!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c77d6-109">[!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]</span></span>  
  
2.  <span data-ttu-id="c77d6-110">Usare un blocco `Try...Catch` per rilevare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c77d6-110">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     <span data-ttu-id="c77d6-111">[!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c77d6-111">[!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]</span></span>  
  
3.  <span data-ttu-id="c77d6-112">Inserire il codice che potrebbe generare un'eccezione nel blocco `Try`.</span><span class="sxs-lookup"><span data-stu-id="c77d6-112">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="c77d6-113">Rimuovere il commento dalle righe `Dim` e `MsgBox` per causare un'eccezione <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="c77d6-113">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     <span data-ttu-id="c77d6-114">[!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c77d6-114">[!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]</span></span>  
  
4.  <span data-ttu-id="c77d6-115">Nel blocco `Catch` usare il metodo `My.Application.Log.WriteException` per scrivere le informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c77d6-115">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     <span data-ttu-id="c77d6-116">[!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c77d6-116">[!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]</span></span>  
  
     <span data-ttu-id="c77d6-117">L'esempio seguente illustra il codice completo per registrare un'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="c77d6-117">The following example shows the complete code for logging a handled exception.</span></span>  
  
     <span data-ttu-id="c77d6-118">[!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="c77d6-118">[!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]</span></span>  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="c77d6-119">Per registrare un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="c77d6-119">To log an unhandled exception</span></span>  
  
1.  <span data-ttu-id="c77d6-120">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c77d6-121">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-121">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="c77d6-122">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="c77d6-122">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="c77d6-123">Fare clic sul pulsante **Visualizza eventi applicazione** per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="c77d6-123">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="c77d6-124">Verrà aperto il file ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="c77d6-124">This opens the ApplicationEvents.vb file.</span></span>  
  
4.  <span data-ttu-id="c77d6-125">Aprire il file ApplicationEvents.vb nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="c77d6-125">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="c77d6-126">Scegliere **Eventi MyApplication** dal menu **Generale**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-126">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5.  <span data-ttu-id="c77d6-127">Scegliere **UnhandledException** dal menu **Dichiarazioni**.</span><span class="sxs-lookup"><span data-stu-id="c77d6-127">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="c77d6-128">L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> prima dell'esecuzione dell'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="c77d6-128">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6.  <span data-ttu-id="c77d6-129">Aggiungere il metodo `My.Application.Log.WriteException` al gestore eventi `UnhandledException` .</span><span class="sxs-lookup"><span data-stu-id="c77d6-129">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     <span data-ttu-id="c77d6-130">[!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="c77d6-130">[!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]</span></span>  
  
     <span data-ttu-id="c77d6-131">L'esempio seguente illustra il codice completo per registrare un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="c77d6-131">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     <span data-ttu-id="c77d6-132">[!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="c77d6-132">[!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77d6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c77d6-133">See Also</span></span>  
 <span data-ttu-id="c77d6-134"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c77d6-134"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="c77d6-135"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="c77d6-135"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="c77d6-136"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="c77d6-136"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="c77d6-137">[Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="c77d6-137">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="c77d6-138">[Procedura: Scrivere messaggi di log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c77d6-138">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="c77d6-139">[Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="c77d6-139">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 [<span data-ttu-id="c77d6-140">Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="c77d6-140">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

