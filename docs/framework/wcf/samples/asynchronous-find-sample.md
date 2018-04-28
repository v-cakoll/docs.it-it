---
title: Esempio di ricerca asincrona
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1545791eceae6d4651ca5299a84623466e8b4976
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="asynchronous-find-sample"></a><span data-ttu-id="04cd6-102">Esempio di ricerca asincrona</span><span class="sxs-lookup"><span data-stu-id="04cd6-102">Asynchronous Find Sample</span></span>
<span data-ttu-id="04cd6-103">In questo esempio viene illustrato come utilizzare l'operazione di ricerca asincrona da un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="04cd6-103">This sample shows how to use the asynchronous find operation from a client application.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="04cd6-104">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="04cd6-104">Sample Details</span></span>  
 <span data-ttu-id="04cd6-105">Il vantaggio di attenersi a questo modello di progettazione è che il client riceve una notifica in modo asincrono relativa agli endpoint individuati come risultato della richiesta di ricerca.</span><span class="sxs-lookup"><span data-stu-id="04cd6-105">The benefit of following this design pattern is that the client is notified asynchronously of the endpoints located as a result of the find request.</span></span> <span data-ttu-id="04cd6-106">Per visualizzare il funzionamento dell'esempio, aprire il file Client.cs.</span><span class="sxs-lookup"><span data-stu-id="04cd6-106">To see how this works, open the Client.cs file.</span></span> <span data-ttu-id="04cd6-107">Si noti che l'oggetto <xref:System.ServiceModel.Discovery.DiscoveryClient> dispone di due delegati allegati ai gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="04cd6-107">Note the <xref:System.ServiceModel.Discovery.DiscoveryClient> object has two delegates attached to its event handlers.</span></span> <span data-ttu-id="04cd6-108">Un delegato viene chiamato quando viene generato un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>, mentre l'altro viene chiamato ogni volta che viene generato un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.</span><span class="sxs-lookup"><span data-stu-id="04cd6-108">One delegate is called when a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is raised and another is called each time a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> event is raised.</span></span> <span data-ttu-id="04cd6-109">L'esempio mostra come è possibile usare questo modello nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="04cd6-109">The sample shows how you can utilize this pattern in your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04cd6-110">L'esempio utilizza endpoint HTTP e, per eseguirlo, è necessario aggiungere ACL URL appropriati.</span><span class="sxs-lookup"><span data-stu-id="04cd6-110">This sample uses HTTP endpoints and to run, proper URL ACLs must be added.</span></span> <span data-ttu-id="04cd6-111">Per altre informazioni, vedere [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="04cd6-111">For more information, see [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="04cd6-112">L'esecuzione del comando seguente con privilegi elevati consente di aggiungere gli elenchi di controllo di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="04cd6-112">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="04cd6-113">È possibile sostituire dominio e nome utente per gli argomenti seguenti se il comando non funziona in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="04cd6-113">You may want to substitute your domain and username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="04cd6-114">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="04cd6-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="04cd6-115">Utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], aprire AsyncFind.sln.</span><span class="sxs-lookup"><span data-stu-id="04cd6-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the AsyncFind.sln.</span></span>  
  
2.  <span data-ttu-id="04cd6-116">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="04cd6-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="04cd6-117">Aprire il prompt dei comandi di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] e passare alla directory \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug o alla directory \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug ed eseguire Service.exe.</span><span class="sxs-lookup"><span data-stu-id="04cd6-117">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug or \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug directory and run Service.exe.</span></span>  
  
4.  <span data-ttu-id="04cd6-118">Una volta avviato il servizio, passare alla directory \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug o alla directory WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug ed eseguire Client.exe.</span><span class="sxs-lookup"><span data-stu-id="04cd6-118">After the service has started, navigate to the \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug or WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug directory and run Client.exe.</span></span>  
  
5.  <span data-ttu-id="04cd6-119">Si noti che il client è in grado di individuare e chiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="04cd6-119">Observe the client is able to locate and call the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="04cd6-120">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="04cd6-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="04cd6-121">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="04cd6-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="04cd6-122">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04cd6-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="04cd6-123">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="04cd6-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a><span data-ttu-id="04cd6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04cd6-124">See Also</span></span>
