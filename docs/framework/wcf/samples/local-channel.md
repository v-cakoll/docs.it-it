---
title: Canale locale
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 87e140395ac2fb5702d8655cf970da8a60c991ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144507"
---
# <a name="local-channel"></a><span data-ttu-id="0971d-102">Canale locale</span><span class="sxs-lookup"><span data-stu-id="0971d-102">Local Channel</span></span>
<span data-ttu-id="0971d-103">Canale locale è un canale di trasporto di Windows Communication Foundation (WCF) che viene utilizzato per la comunicazione all'interno dello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="0971d-103">Local Channel is a Windows Communication Foundation (WCF) transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="0971d-104">È utile negli scenari in cui il client e il servizio sono in esecuzione nello stesso dominio applicazione e l'overhead dello stack di canali WCF tipico (serializzazione e deserializzazione di messaggi) deve essere evitato.</span><span class="sxs-lookup"><span data-stu-id="0971d-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="0971d-105">Dimostra</span><span class="sxs-lookup"><span data-stu-id="0971d-105">Demonstrates</span></span>  
 <span data-ttu-id="0971d-106">Canale locale</span><span class="sxs-lookup"><span data-stu-id="0971d-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="0971d-107">Discussione</span><span class="sxs-lookup"><span data-stu-id="0971d-107">Discussion</span></span>  
 <span data-ttu-id="0971d-108">L'esempio è costituito da due file di progetto:</span><span class="sxs-lookup"><span data-stu-id="0971d-108">The sample consists of two project files:</span></span>  
  
- <span data-ttu-id="0971d-109">**LocalChannel**: rappresentazione a livello di codice del canale locale all'interno del dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="0971d-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="0971d-110">In questo progetto il componente di invio posiziona il messaggio in una coda in memoria e il componente ricevente rimuovere il messaggio dalla coda per riceverlo.</span><span class="sxs-lookup"><span data-stu-id="0971d-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
- <span data-ttu-id="0971d-111">**ClientAndService:** questo progetto ospita un servizio in un'applicazione console e quindi esegue un client per chiamare il servizio dall'interno dello stesso dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="0971d-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="0971d-112">Per aumentare la velocità, la progettazione del canale locale ignora sia lo stack di canali che il processo di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="0971d-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="0971d-113">Il canale di trasporto locale viene implementato usando una coda per il trasporto delle chiamate al servizio dal client al servizio e per restituire il valore al client.</span><span class="sxs-lookup"><span data-stu-id="0971d-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="0971d-114">Anziché parametri di serializzazione e valori restituiti, nell'esempio vengono copiati gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="0971d-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0971d-115">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0971d-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0971d-116">Compilare ed eseguire la soluzione LocalChannel.</span><span class="sxs-lookup"><span data-stu-id="0971d-116">Build and run the LocalChannel solution.</span></span>  
  
2. <span data-ttu-id="0971d-117">L'host del servizio viene iniziato e il client chiama il servizio usando il canale locale.</span><span class="sxs-lookup"><span data-stu-id="0971d-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="0971d-118">Viene visualizzata una finestra della console contenente i risultati della chiamata al servizio.</span><span class="sxs-lookup"><span data-stu-id="0971d-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0971d-119">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0971d-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0971d-120">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0971d-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0971d-121">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0971d-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0971d-122">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0971d-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
