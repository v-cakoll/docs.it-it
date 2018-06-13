---
title: Ricezione memorizzata nel buffer
ms.date: 03/30/2017
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
ms.openlocfilehash: ee53edafc94fd5efd4e412b1b9198a8763b79462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518711"
---
# <a name="buffered-receive"></a><span data-ttu-id="4317e-102">Ricezione memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="4317e-102">Buffered Receive</span></span>
<span data-ttu-id="4317e-103">In questo esempio viene illustrato come impostare e configurare la funzionalità di ricezione memorizzata nel buffer in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="4317e-103">This sample demonstrates how to set up and configure the buffered receive feature in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="4317e-104">La ricezione memorizzata nel buffer consente a un autore di creare un flusso di lavoro senza dover preoccuparsi dell'ordine con cui vengono ricevuti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="4317e-104">Buffered receive allows the workflow author to create a workflow without having to worry about the order in which messages are received.</span></span> <span data-ttu-id="4317e-105">La funzionalità di ricezione memorizzata nel buffer memorizza localmente nel buffer i messaggi e li recapita quando il flusso di lavoro è pronto per riceverli.</span><span class="sxs-lookup"><span data-stu-id="4317e-105">The buffered receive feature buffers messages locally and delivers them when the workflow is ready to receive them.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4317e-106">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="4317e-106">Demonstrates</span></span>  
 <span data-ttu-id="4317e-107">Elaborazione di messaggi non ordinata tramite la ricezione memorizzata nel buffer con attività di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="4317e-107">Out-of-order message processing using buffered receive with messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4317e-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4317e-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4317e-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4317e-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4317e-110">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="4317e-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4317e-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4317e-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a><span data-ttu-id="4317e-112">Discussione</span><span class="sxs-lookup"><span data-stu-id="4317e-112">Discussion</span></span>  
 <span data-ttu-id="4317e-113">In questo esempio, un servizio Windows Communication Foundation (WCF) viene implementato usando [!INCLUDE[wf1](../../../../includes/wf1-md.md)] e dispone di una sequenza di <xref:System.ServiceModel.Activities.Receive> le attività.</span><span class="sxs-lookup"><span data-stu-id="4317e-113">In this sample, a Windows Communication Foundation (WCF) service is implemented using [!INCLUDE[wf1](../../../../includes/wf1-md.md)] and has a sequence of <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="4317e-114">Questo flusso di lavoro modella un semplice processo di approvazione di un prestito in cui il flusso di lavoro prevede l'approvazione di tre notifiche per un prestito.</span><span class="sxs-lookup"><span data-stu-id="4317e-114">This workflow models a simple loan approval process where the workflow expects three notifications for a loan to be approved.</span></span> <span data-ttu-id="4317e-115">Un'applicazione client Windows Communication Foundation (WCF) invia tre notifiche correlate nell'ordine inverso rispetto a quello previsto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="4317e-115">A Windows Communication Foundation (WCF) client application sends three correlated notifications in the reverse order of what the service expects.</span></span> <span data-ttu-id="4317e-116">Poiché la funzionalità di ricezione memorizzata nel buffer viene attivata in corrispondenza del servizio, ogni messaggio non ordinato viene memorizzato nel buffer in corrispondenza del servizio ed elaborato quando il flusso di lavoro diventa pronto per riceverlo.</span><span class="sxs-lookup"><span data-stu-id="4317e-116">Because the buffered receive feature is turned on at the service, each out-of-order message is buffered at the service and processed as the workflow becomes ready to receive it.</span></span>  
  
 <span data-ttu-id="4317e-117">La funzionalità di ricezione memorizzata nel buffer richiede che l'associazione supporti l'oggetto <xref:System.ServiceModel.Activities.ReceiveContent>, pertanto il servizio usa l'oggetto <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="4317e-117">The buffered receive feature requires <xref:System.ServiceModel.Activities.ReceiveContent> support from the binding, therefore the service uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="4317e-118">Non è richiesta alcuna configurazione particolare per l'associazione, pertanto vengono usate le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="4317e-118">No special configuration is required for the binding, so the defaults are used.</span></span>  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 <span data-ttu-id="4317e-119">Il servizio espone inoltre i metadati per il servizio tramite l'oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="4317e-119">The service also exposes metadata for the service using <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span></span>  
  
 <span data-ttu-id="4317e-120">Analogamente, l'endpoint client viene configurato usando l'oggetto <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="4317e-120">Similarly, the client endpoint is configured using <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="4317e-121">Il codice client e la configurazione viene generato utilizzando la **Aggiungi riferimento al servizio** funzionalità di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4317e-121">The client code and configuration is generated by using the **Add Service Reference** feature of Visual Studio.</span></span> <span data-ttu-id="4317e-122">L'esempio seguente rappresenta l'endpoint client generato nel file App.config.</span><span class="sxs-lookup"><span data-stu-id="4317e-122">The following example is the generated client endpoint in the App.config file.</span></span>  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 <span data-ttu-id="4317e-123">Per questo esempio è necessario aver abilitato i seguenti componenti di Windows:</span><span class="sxs-lookup"><span data-stu-id="4317e-123">This sample requires that the following Windows components are enabled:</span></span>  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  <span data-ttu-id="4317e-124">Compatibilità di gestione, compatibilità metabase e compatibilità configurazione di [!INCLUDE[iis60](../../../../includes/iis60-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4317e-124">[!INCLUDE[iis60](../../../../includes/iis60-md.md)] Management Compatibility, Metabase, and Configuration Compatibility</span></span>  
  
3.  <span data-ttu-id="4317e-125">Servizi World Wide Web, funzionalità di sviluppo di applicazioni e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4317e-125">World Wide Web Services, Application Development Features, and ASP.NET</span></span>  
  
4.  <span data-ttu-id="4317e-126">Microsoft Message Queue (MSMQ) Server</span><span class="sxs-lookup"><span data-stu-id="4317e-126">Microsoft Message Queues (MSMQ) Server</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="4317e-127">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="4317e-127">To set up, and build the sample</span></span>  
  
1.  <span data-ttu-id="4317e-128">In corrispondenza di un prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], registrare ASP.NET digitando `aspnet_regiis –I` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="4317e-128">At a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by typing `aspnet_regiis –I` and press ENTER.</span></span>  
  
2.  <span data-ttu-id="4317e-129">Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] come amministratore.</span><span class="sxs-lookup"><span data-stu-id="4317e-129">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an Administrator.</span></span>  
  
3.  <span data-ttu-id="4317e-130">Aprire LoanService.sln.</span><span class="sxs-lookup"><span data-stu-id="4317e-130">Open LoanService.sln.</span></span>  
  
4.  <span data-ttu-id="4317e-131">Quando viene richiesto se si desidera creare directory virtuali per il progetto LoanService, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4317e-131">When asked if you would like to create the virtual directories for the LoanService project, select **Yes**.</span></span>  
  
#### <a name="to-set-up-the-service-queues"></a><span data-ttu-id="4317e-132">Per impostare le code del servizio</span><span class="sxs-lookup"><span data-stu-id="4317e-132">To set up the service queues</span></span>  
  
1.  <span data-ttu-id="4317e-133">Premere F5 per eseguire l'applicazione LoanClient che crea le code e attiva il servizio definito in Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="4317e-133">Press F5 to run the LoanClient application that creates the queues and activates the service defined in Service1.xamlx.</span></span>  
  
2.  <span data-ttu-id="4317e-134">Aprire il **Gestione Computer** console eseguendo Compmgmt.msc da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4317e-134">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
3.  <span data-ttu-id="4317e-135">Nel **Gestione Computer** espandere **servizio**, **applicazioni**, **Accodamento**, **code Private** .</span><span class="sxs-lookup"><span data-stu-id="4317e-135">In the **Computer Management** console, expand **Service**, **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
4.  <span data-ttu-id="4317e-136">La coda loanservice/service1.xamlx di mouse e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4317e-136">Right-click the loanservice/service1.xamlx queue and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="4317e-137">Selezionare il **sicurezza** scheda e aggiungere **tutti ricevono messaggi**, **Visualizza il messaggio** e **Invia messaggio** autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4317e-137">Select the **Security** tab, and add **Everyone Receives Message**, **Peek Message** and **Send Message** permissions.</span></span>  
  
6.  <span data-ttu-id="4317e-138">Aprire Gestione [!INCLUDE[iis60](../../../../includes/iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4317e-138">Open the [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Manager.</span></span>  
  
7.  <span data-ttu-id="4317e-139">Passare a **Server**, **siti**, **Default Web site**, **privata**, **LoanService** e selezionare  **Opzioni avanzate**</span><span class="sxs-lookup"><span data-stu-id="4317e-139">Browse to **Server**, **Sites**, **Default Web site**, **Private**, **LoanService** and select **Advanced Options**</span></span>  
  
8.  <span data-ttu-id="4317e-140">Modifica il **protocolli abilitati** da **http**, **NET. MSMQ**.</span><span class="sxs-lookup"><span data-stu-id="4317e-140">Change the **Enabled Protocols** to be **http**, **net.msmq**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="4317e-141">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="4317e-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="4317e-142">Passare a http://localhost/private/loanservice/service1.xamlx per garantire che il servizio sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4317e-142">Browse to http://localhost/private/loanservice/service1.xamlx to ensure that the service is running.</span></span>  
  
2.  <span data-ttu-id="4317e-143">Premere F5 per eseguire l'applicazione LoanClient.</span><span class="sxs-lookup"><span data-stu-id="4317e-143">Press F5 to run the LoanClient application.</span></span> <span data-ttu-id="4317e-144">Una volta completato il flusso di lavoro, è necessario salvare un file out.txt nella directory C:\Inbox in cui è contenuto il risultato dello scambio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="4317e-144">Once the workflow is complete, an out.txt file should be saved to C:\Inbox that contains the result of the message exchange.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="4317e-145">Per eseguire la pulizia</span><span class="sxs-lookup"><span data-stu-id="4317e-145">To clean up</span></span>  
  
1.  <span data-ttu-id="4317e-146">Aprire il **Gestione Computer** console eseguendo Compmgmt.msc da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4317e-146">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
2.  <span data-ttu-id="4317e-147">Espandere **servizio** e **applicazioni**, **Accodamento**, **code Private**.</span><span class="sxs-lookup"><span data-stu-id="4317e-147">Expand **Service** and **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="4317e-148">Eliminare la coda loanservice/service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="4317e-148">Delete the loanservice/service1.xamlx queue.</span></span>  
  
4.  <span data-ttu-id="4317e-149">Rimuovere la directory C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="4317e-149">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4317e-150">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4317e-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4317e-151">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4317e-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4317e-152">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="4317e-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4317e-153">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4317e-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
