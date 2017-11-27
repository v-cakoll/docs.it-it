---
title: Canale locale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dee09b8f7b1e48a84fa79381d44fe48a4da16129
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="local-channel"></a><span data-ttu-id="ae280-102">Canale locale</span><span class="sxs-lookup"><span data-stu-id="ae280-102">Local Channel</span></span>
<span data-ttu-id="ae280-103">Il canale locale è un canale di trasporto di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] usato per la comunicazione all'interno dello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae280-103">Local Channel is a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="ae280-104">È utile negli scenari in cui il client e il servizio sono in esecuzione nello stesso dominio applicazione e l'overhead dello stack di canali WCF tipico (serializzazione e deserializzazione di messaggi) deve essere evitato.</span><span class="sxs-lookup"><span data-stu-id="ae280-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ae280-105">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="ae280-105">Demonstrates</span></span>  
 <span data-ttu-id="ae280-106">Canale locale</span><span class="sxs-lookup"><span data-stu-id="ae280-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ae280-107">Discussione</span><span class="sxs-lookup"><span data-stu-id="ae280-107">Discussion</span></span>  
 <span data-ttu-id="ae280-108">L'esempio è costituito da due file di progetto:</span><span class="sxs-lookup"><span data-stu-id="ae280-108">The sample consists of two project files:</span></span>  
  
-   <span data-ttu-id="ae280-109">**LocalChannel**: rappresentazione a livello del canale locale all'interno del dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ae280-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="ae280-110">In questo progetto il componente di invio posiziona il messaggio in una coda in memoria e il componente ricevente rimuovere il messaggio dalla coda per riceverlo.</span><span class="sxs-lookup"><span data-stu-id="ae280-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
-   <span data-ttu-id="ae280-111">**ClientAndService**: questo progetto ospita un servizio in un'applicazione console e quindi esegue un client per chiamare il servizio dall'interno dello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae280-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="ae280-112">Per aumentare la velocità, la progettazione del canale locale ignora sia lo stack di canali che il processo di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="ae280-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="ae280-113">Il canale di trasporto locale viene implementato usando una coda per il trasporto delle chiamate al servizio dal client al servizio e per restituire il valore al client.</span><span class="sxs-lookup"><span data-stu-id="ae280-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="ae280-114">Anziché parametri di serializzazione e valori restituiti, nell'esempio vengono copiati gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="ae280-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ae280-115">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ae280-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ae280-116">Compilare ed eseguire la soluzione LocalChannel.</span><span class="sxs-lookup"><span data-stu-id="ae280-116">Build and run the LocalChannel solution.</span></span>  
  
2.  <span data-ttu-id="ae280-117">L'host del servizio viene iniziato e il client chiama il servizio usando il canale locale.</span><span class="sxs-lookup"><span data-stu-id="ae280-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="ae280-118">Viene visualizzata una finestra della console contenente i risultati della chiamata al servizio.</span><span class="sxs-lookup"><span data-stu-id="ae280-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae280-119">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ae280-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ae280-120">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ae280-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ae280-121">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae280-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ae280-122">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ae280-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
