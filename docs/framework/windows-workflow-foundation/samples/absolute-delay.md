---
title: Ritardo assoluto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b483139a-39bb-4560-8003-8969a8fc2cd1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 94eb9f401786ef05beaa51077ff4ddc170595752
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="absolute-delay"></a><span data-ttu-id="ba963-102">Ritardo assoluto</span><span class="sxs-lookup"><span data-stu-id="ba963-102">Absolute Delay</span></span>
<span data-ttu-id="ba963-103">Lo scenario principale di questo esempio è ritardare un flusso di lavoro fino a una <xref:System.DateTime> specificata usando timer durevoli in un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ba963-103">The main scenario for this sample is to delay until a specified <xref:System.DateTime> using durable timers in a workflow application.</span></span> <span data-ttu-id="ba963-104">Si tratta di uno scenario diverso rispetto all'utilizzo dell'attività <xref:System.Activities.Statements.Delay> incorporata in quanto in questo caso sarà possibile ritardare un flusso di lavoro solo per un determinato <xref:System.TimeSpan> (o numero di minuti/secondi).</span><span class="sxs-lookup"><span data-stu-id="ba963-104">This is different from using the built-in <xref:System.Activities.Statements.Delay> activity as this will only allow you to delay for a given <xref:System.TimeSpan> (or number of minutes/seconds).</span></span>  
  
 <span data-ttu-id="ba963-105">Di seguito sono elencati alcuni scenari reali nei quali potrebbe essere necessario fare questa distinzione:</span><span class="sxs-lookup"><span data-stu-id="ba963-105">Some real-life scenarios in which you may want to make this distinction include the following:</span></span>  
  
1.  <span data-ttu-id="ba963-106">Si desidera ritardare di 30 secondi l'invio di un messaggio di posta elettronica per verificare che non contenga errori.</span><span class="sxs-lookup"><span data-stu-id="ba963-106">You want to delay sending a mail for 30 seconds to make sure you didn’t make any errors.</span></span>  
  
2.  <span data-ttu-id="ba963-107">In caso di straordinari sul lavoro, si desidera ritardare l'invio di tutti i messaggi di posta elettronica fino al normale orario di lavoro (ad esempio 8 del mattino).</span><span class="sxs-lookup"><span data-stu-id="ba963-107">You are working overtime and want to delay all of your mails until normal business hours (such as 8 am).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ba963-108">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="ba963-108">Demonstrates</span></span>  
  
1.  <span data-ttu-id="ba963-109"><xref:System.Activities.Statements.DurableTimerExtension> per l'implementazione del ritardo assoluto</span><span class="sxs-lookup"><span data-stu-id="ba963-109"><xref:System.Activities.Statements.DurableTimerExtension> for implementing Absolute Delay</span></span>  
  
2.  <span data-ttu-id="ba963-110">Configurazione della persistenza usando <xref:System.Activities.WorkflowApplication> per timer durevoli</span><span class="sxs-lookup"><span data-stu-id="ba963-110">Setting up persistence using <xref:System.Activities.WorkflowApplication> for Durable Timers</span></span>  
  
3.  <span data-ttu-id="ba963-111">Uso di <xref:System.Activities.NativeActivity%601> per i punti di estensibilità</span><span class="sxs-lookup"><span data-stu-id="ba963-111">Use of <xref:System.Activities.NativeActivity%601> for using Extensibility points</span></span>  
  
4.  <span data-ttu-id="ba963-112">Uso di <xref:System.Activities.CodeActivity%601> nell'attività SendEmail.</span><span class="sxs-lookup"><span data-stu-id="ba963-112">Use of <xref:System.Activities.CodeActivity%601> in the SendEmail activity</span></span>  
  
5.  <xref:System.Activities.Statements.Delay>  
  
6.  <span data-ttu-id="ba963-113">Flusso di lavoro solo XAML</span><span class="sxs-lookup"><span data-stu-id="ba963-113">XAML-only workflow</span></span>  
  
 <span data-ttu-id="ba963-114">Questo esempio dimostra come creare un'attività personalizzata che accetta una <xref:System.DateTime> e usa timer durevoli per registrare la durata del ritardo.</span><span class="sxs-lookup"><span data-stu-id="ba963-114">This sample demonstrates how to create a custom activity which takes in a <xref:System.DateTime> and uses durable timers to register the delay duration.</span></span> <span data-ttu-id="ba963-115">In caso di utilizzo di timer durevoli, è necessario usare un'attività <xref:System.Activities.NativeActivity> per creare un segnalibro, in quanto è necessario registrare questo segnalibro con l'estensione del timer.</span><span class="sxs-lookup"><span data-stu-id="ba963-115">When using durable timers, you must use a <xref:System.Activities.NativeActivity> to create a bookmark, as you will need to register this bookmark with the timer extension.</span></span> <span data-ttu-id="ba963-116">In questo esempio, quando il timer durevole scade, viene chiamato il metodo `OnTimerExpired`.</span><span class="sxs-lookup"><span data-stu-id="ba963-116">In this sample, when the durable timer expires, the `OnTimerExpired` method will be called.</span></span> <span data-ttu-id="ba963-117">Verificare che l'estensione del timer venga aggiunta all'evento <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> per garantire che venga fornito il runtime con queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="ba963-117">Make sure that you are adding the timer extension in the <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> event to ensure you are providing the runtime with this information.</span></span> <span data-ttu-id="ba963-118">Come unico altro dettaglio di implementazione, sarà necessario implementare la logica per la conversione da <xref:System.DateTime> a <xref:System.TimeSpan>, in quanto i timer durevoli accettano solo <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="ba963-118">The only other implementation detail is that you will need to implement logic to convert from <xref:System.DateTime> to <xref:System.TimeSpan>, as durable timers only take in a <xref:System.DateTime>.</span></span> <span data-ttu-id="ba963-119">Notare la piccola perdita di precisione.</span><span class="sxs-lookup"><span data-stu-id="ba963-119">Do note that there is a small lapse in accuracy by doing</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba963-120">La conversione da <xref:System.DateTime> a <xref:System.TimeSpan> determina una minima perdita di precisione.</span><span class="sxs-lookup"><span data-stu-id="ba963-120">There is a small loss of accuracy by converting from <xref:System.DateTime> to <xref:System.TimeSpan>.</span></span>  
  
 <span data-ttu-id="ba963-121">Questo esempio dimostra inoltre come attivare la persistenza per una <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="ba963-121">This sample also demonstrates how to turn on persistence for a <xref:System.Activities.WorkflowApplication>.</span></span> <span data-ttu-id="ba963-122">Per questo particolare esempio, verranno usati timer durevoli in cui i dati del flusso di lavoro verranno scaricati nel database di persistenza durante il tempo di inattività in attesa della scadenza del timer.</span><span class="sxs-lookup"><span data-stu-id="ba963-122">For this particular sample, we will be using durable timers in which the workflow data will be unloaded into the persistence database during the idle time while waiting for timer to expire.</span></span> <span data-ttu-id="ba963-123">Questa implementazione può essere usata anche per altre azioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="ba963-123">This implementation can also be used for other persistence actions.</span></span> <span data-ttu-id="ba963-124">Questo esempio mostra come configurare la stringa di connessione della persistenza con SQL Server e come creare l'archivio di istanze per rendere persistenti i dati delle istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ba963-124">This sample shows how to set up the persistence connection string with SQL Server, and how to create the instance store in order to persist the data for workflow instances.</span></span> <span data-ttu-id="ba963-125">Viene fornita la logica per riprendere il flusso di lavoro una volta generato un evento che rende eseguibile l'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ba963-125">Logic is provided on how to resume the workflow once an event is raised which makes the workflow instance runnable.</span></span>  
  
 <span data-ttu-id="ba963-126">Nel corso di questo esempio verrà mostrato il momento di inizio e fine del ritardo incorporato, che a sua volta determina l'invio di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ba963-126">As you step through this sample, you will see the time in which the built-in delay begins and completes, which in turn will cause an e-mail message to be sent.</span></span> <span data-ttu-id="ba963-127">A questo punto, l'attività AbsoluteDelay verrà interrotta fino a una determinata <xref:System.DateTime> (o 0 secondi se <xref:System.DateTime> è scaduta), che a sua volta invierà un messaggio di posta elettronica alla scadenza.</span><span class="sxs-lookup"><span data-stu-id="ba963-127">From there, the AbsoluteDelay activity will halt until a specified <xref:System.DateTime> (or 0 seconds if the <xref:System.DateTime> has expired) which in turn will send out an email upon expiration.</span></span> <span data-ttu-id="ba963-128">In questo modo verranno mostrati i due diversi casi di utilizzo della funzionalità <xref:System.Activities.Statements.Delay> incorporata rispetto all'utilizzo di un'attività AbsoluteDelay.</span><span class="sxs-lookup"><span data-stu-id="ba963-128">This will show the two different use cases of the built-in <xref:System.Activities.Statements.Delay> functionality versus using an AbsoluteDelay activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ba963-129">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ba963-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ba963-130">Verificare che sul computer sia installato SQL Server Express (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="ba963-130">Ensure you have SQL Server Express (or higher) installed on your machine</span></span>  
  
2.  <span data-ttu-id="ba963-131">Eseguire setup.cmd (da WF/Basic/Services/AbsoluteDelay/CS) in un prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] per creare il database AbsoluteDelaySampleDB, lo schema di persistenza e la logica di persistenza.</span><span class="sxs-lookup"><span data-stu-id="ba963-131">Run setup.cmd (from WF/Basic/Services/AbsoluteDelay/CS) in a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt to create the AbsoluteDelaySampleDB database, create the persistence schema and create the persistence logic.</span></span>  
  
3.  <span data-ttu-id="ba963-132">Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba963-132">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="ba963-133">Specificare Duration nell'attività Delay.</span><span class="sxs-lookup"><span data-stu-id="ba963-133">Specify the Duration in the Delay activity.</span></span>  
  
5.  <span data-ttu-id="ba963-134">Specificare ExpirationTime nell'attività AbsoluteDelay.</span><span class="sxs-lookup"><span data-stu-id="ba963-134">Specify the ExpirationTime in the AbsoluteDelay activity.</span></span>  
  
6.  <span data-ttu-id="ba963-135">Aggiornare i campi SendMailTo, SendMailFrom, SendMailSubject, SendMailBody e SmtpHost nell'attività SendMail.</span><span class="sxs-lookup"><span data-stu-id="ba963-135">Update the SendMailTo, SendMailFrom, SendMailSubject, SendMailBody, and SmtpHost fields in the SendMail activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba963-136">Se non si specifica un host SMTP valido, l'applicazione genera un'eccezione SMTP.</span><span class="sxs-lookup"><span data-stu-id="ba963-136">If you do not enter a valid SMTP host, the application will throw a SMTP exception.</span></span>  
  
7.  <span data-ttu-id="ba963-137">Compilare la soluzione selezionando **compilare**, **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="ba963-137">Build the solution by selecting **Build**, **Build Solution**.</span></span>  
  
8.  <span data-ttu-id="ba963-138">Eseguire la soluzione premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="ba963-138">Run the solution by pressing **F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba963-139">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ba963-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ba963-140">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ba963-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ba963-141">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba963-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ba963-142">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ba963-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\AbsoluteDelay`
