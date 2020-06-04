---
title: 'Procedura: Registrare eccezioni'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: 59ed7b836126a38f32b7c6f479570a566d236e6c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410114"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="9f5d2-102">Procedura: registrare eccezioni in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f5d2-102">How to: Log Exceptions in Visual Basic</span></span>

<span data-ttu-id="9f5d2-103">È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sulle eccezioni generate nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="9f5d2-104">Questi esempi illustrano come usare il metodo `My.Application.Log.WriteException` per registrare le eccezioni rilevate in modo esplicito e quelle non gestite.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="9f5d2-105">Per registrare le informazioni di traccia, usare il metodo `My.Application.Log.WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="9f5d2-106">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="9f5d2-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="9f5d2-107">Per registrare un'eccezione gestita</span><span class="sxs-lookup"><span data-stu-id="9f5d2-107">To log a handled exception</span></span>  
  
1. <span data-ttu-id="9f5d2-108">Creare il metodo che genererà le informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-108">Create the method that will generate the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#9)]  
  
2. <span data-ttu-id="9f5d2-109">Usare un blocco `Try...Catch` per rilevare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-109">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#6)]  
  
3. <span data-ttu-id="9f5d2-110">Inserire il codice che potrebbe generare un'eccezione nel blocco `Try`.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-110">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="9f5d2-111">Rimuovere il commento dalle righe `Dim` e `MsgBox` per causare un'eccezione <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-111">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#7)]  
  
4. <span data-ttu-id="9f5d2-112">Nel blocco `Catch` usare il metodo `My.Application.Log.WriteException` per scrivere le informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-112">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#8)]  
  
     <span data-ttu-id="9f5d2-113">L'esempio seguente illustra il codice completo per registrare un'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-113">The following example shows the complete code for logging a handled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#10)]  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="9f5d2-114">Per registrare un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="9f5d2-114">To log an unhandled exception</span></span>  
  
1. <span data-ttu-id="9f5d2-115">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-115">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9f5d2-116">Scegliere **Proprietà**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="9f5d2-116">On the **Project** menu, choose **Properties**.</span></span>  
  
2. <span data-ttu-id="9f5d2-117">Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="9f5d2-117">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="9f5d2-118">Fare clic sul pulsante **Visualizza eventi applicazione** per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-118">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="9f5d2-119">Verrà aperto il file ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-119">This opens the ApplicationEvents.vb file.</span></span>  
  
4. <span data-ttu-id="9f5d2-120">Aprire il file ApplicationEvents.vb nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-120">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="9f5d2-121">Scegliere **Eventi MyApplication** dal menu **Generale**.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-121">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5. <span data-ttu-id="9f5d2-122">Scegliere **UnhandledException** dal menu **Dichiarazioni**.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-122">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="9f5d2-123">L'applicazione genera l'evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> prima dell'esecuzione dell'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-123">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6. <span data-ttu-id="9f5d2-124">Aggiungere il metodo `My.Application.Log.WriteException` al gestore eventi `UnhandledException` .</span><span class="sxs-lookup"><span data-stu-id="9f5d2-124">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#4)]  
  
     <span data-ttu-id="9f5d2-125">L'esempio seguente illustra il codice completo per registrare un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="9f5d2-125">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="9f5d2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f5d2-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="9f5d2-127">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="9f5d2-127">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="9f5d2-128">Procedura: Scrivere messaggi di log</span><span class="sxs-lookup"><span data-stu-id="9f5d2-128">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)
- [<span data-ttu-id="9f5d2-129">Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="9f5d2-129">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="9f5d2-130">Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="9f5d2-130">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
