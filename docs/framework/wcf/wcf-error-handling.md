---
title: Gestione errori WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26dfea83400b5d601fabc5cfb52bc71a4d5e4f6f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-error-handling"></a><span data-ttu-id="9c6ea-102">Gestione errori WCF</span><span class="sxs-lookup"><span data-stu-id="9c6ea-102">WCF Error Handling</span></span>
<span data-ttu-id="9c6ea-103">Gli errori rilevati da un'applicazione WCF appartengono a uno dei seguenti tre gruppi:</span><span class="sxs-lookup"><span data-stu-id="9c6ea-103">The errors encountered by a WCF application belong to one of three groups:</span></span>  
  
1.  <span data-ttu-id="9c6ea-104">errori di comunicazione</span><span class="sxs-lookup"><span data-stu-id="9c6ea-104">Communication Errors</span></span>  
  
2.  <span data-ttu-id="9c6ea-105">errori di proxy/canale</span><span class="sxs-lookup"><span data-stu-id="9c6ea-105">Proxy/Channel Errors</span></span>  
  
3.  <span data-ttu-id="9c6ea-106">errori di applicazione</span><span class="sxs-lookup"><span data-stu-id="9c6ea-106">Application Errors</span></span>  
  
 <span data-ttu-id="9c6ea-107">Gli errori di comunicazione si verificano quando una rete non è disponibile, un client utilizza un indirizzo errato o l'host del servizio non è in ascolto dei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-107">Communication errors occur when a network is unavailable, a client uses an incorrect address, or the service host is not listening for incoming messages.</span></span> <span data-ttu-id="9c6ea-108">Errori di questo tipo vengono restituiti al client come <xref:System.ServiceModel.CommunicationException> o <xref:System.ServiceModel.CommunicationException> (classi derivate).</span><span class="sxs-lookup"><span data-stu-id="9c6ea-108">Errors of this type are returned to the client as <xref:System.ServiceModel.CommunicationException> or <xref:System.ServiceModel.CommunicationException>-derived classes.</span></span>  
  
 <span data-ttu-id="9c6ea-109">Gli errori di proxy/canale si verificano all'interno del canale o nel proxy stesso.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-109">Proxy/Channel errors are errors that occur within the channel or proxy itself.</span></span> <span data-ttu-id="9c6ea-110">Gli errori di questo tipo includono il tentativo di utilizzare un proxy o un canale chiuso, un contratto non corrispondente tra il client e il servizio o il rifiuto delle credenziali del client da parte del servizio.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-110">Errors of this type include: attempting to use a proxy or channel that has been closed, a contract mismatch exists between the client and service, or the client’s credentials are rejected by the service.</span></span> <span data-ttu-id="9c6ea-111">In questa categoria sono presenti molti tipi di errori diversi, troppo numerosi per essere elencati in questo documento.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-111">There are many different types of errors in this category, too many to list here.</span></span> <span data-ttu-id="9c6ea-112">Gli errori di questo tipo vengono restituiti al client così come sono, non viene eseguita alcuna trasformazione sugli oggetti dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-112">Errors of this type are returned to the client as-is (no transformation is performed on the exception objects).</span></span>  
  
 <span data-ttu-id="9c6ea-113">Gli errori di applicazione si verificano durante l'esecuzione di un'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-113">Application errors occur during the execution of a service operation.</span></span> <span data-ttu-id="9c6ea-114">Errori di questo tipo vengono inviati al client come <xref:System.ServiceModel.FaultException> o <xref:System.ServiceModel.FaultException%601>.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-114">Errors of this kind are sent to the client as <xref:System.ServiceModel.FaultException> or <xref:System.ServiceModel.FaultException%601>.</span></span>  
  
 <span data-ttu-id="9c6ea-115">La gestione degli errori in WCF viene eseguita secondo uno o più dei modi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-115">Error handling in WCF is performed by one or more of the following:</span></span>  
  
-   <span data-ttu-id="9c6ea-116">Gestione diretta dell'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-116">Directly handling the exception thrown.</span></span> <span data-ttu-id="9c6ea-117">Viene eseguita solo per gli errori di comunicazione di proxy/canale.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-117">This is only done for communication and proxy/channel errors.</span></span>  
  
-   <span data-ttu-id="9c6ea-118">Utilizzo dei contratti di errore.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-118">Using fault contracts</span></span>  
  
-   <span data-ttu-id="9c6ea-119">Implementazione dell'interfaccia <xref:System.ServiceModel.Dispatcher.IErrorHandler></span><span class="sxs-lookup"><span data-stu-id="9c6ea-119">Implementing the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface</span></span>  
  
-   <span data-ttu-id="9c6ea-120">Gestione degli eventi <xref:System.ServiceModel.ServiceHost></span><span class="sxs-lookup"><span data-stu-id="9c6ea-120">Handling <xref:System.ServiceModel.ServiceHost> events</span></span>  
  
## <a name="fault-contracts"></a><span data-ttu-id="9c6ea-121">Contratti di errore</span><span class="sxs-lookup"><span data-stu-id="9c6ea-121">Fault Contracts</span></span>  
 <span data-ttu-id="9c6ea-122">I contratti di errore consentono all'utente di definire gli errori che si possono verificare durante l'operazione del servizio in una modalità indipendente dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-122">Fault contracts allow you to define the errors that can occur during service operation in a platform independent way.</span></span> <span data-ttu-id="9c6ea-123">Per impostazione predefinita tutte le eccezioni generate da un'operazione del servizio saranno restituite al client come oggetto <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-123">By default all exceptions thrown from within a service operation will be returned to the client as a <xref:System.ServiceModel.FaultException> object.</span></span> <span data-ttu-id="9c6ea-124">L'oggetto <xref:System.ServiceModel.FaultException> conterrà un numero molto contenuto di informazioni.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-124">The <xref:System.ServiceModel.FaultException> object will contain very little information.</span></span> <span data-ttu-id="9c6ea-125">È possibile controllare le informazioni inviate al client definendo un contratto di errori e restituendo l'errore come <xref:System.ServiceModel.FaultException%601>.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-125">You can control the information sent to the client by defining a fault contract and returning the error as a <xref:System.ServiceModel.FaultException%601>.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="9c6ea-126">[Specifica e gestione di errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="9c6ea-126"> [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
## <a name="ierrorhandler"></a><span data-ttu-id="9c6ea-127">IErrorHandler</span><span class="sxs-lookup"><span data-stu-id="9c6ea-127">IErrorHandler</span></span>  
 <span data-ttu-id="9c6ea-128">L'interfaccia <xref:System.ServiceModel.Dispatcher.IErrorHandler> consente un maggiore controllo delle risposte dell'applicazione WCF agli errori.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-128">The <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface allows you more control over how your WCF application responds to errors.</span></span>  <span data-ttu-id="9c6ea-129">Fornisce controllo completo sul messaggio di errore restituito al client e consente di eseguire elaborazioni personalizzate dell'errore, ad esempio la registrazione.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-129">It gives you full control over the fault message that is returned to the client and allows you to perform custom error processing such as logging.</span></span>  [!INCLUDE[crdefault](../../../includes/crabout-md.md)]<span data-ttu-id="9c6ea-130"><xref:System.ServiceModel.Dispatcher.IErrorHandler> e [estensione del controllo sulla gestione degli errori e Reporting](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)</span><span class="sxs-lookup"><span data-stu-id="9c6ea-130"> <xref:System.ServiceModel.Dispatcher.IErrorHandler> and [Extending Control Over Error Handling and Reporting](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)</span></span>  
  
## <a name="servicehost-events"></a><span data-ttu-id="9c6ea-131">Eventi ServiceHost</span><span class="sxs-lookup"><span data-stu-id="9c6ea-131">ServiceHost Events</span></span>  
 <span data-ttu-id="9c6ea-132">La classe <xref:System.ServiceModel.ServiceHost> ospita i servizi e definisce diversi eventi che possono essere necessari per la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="9c6ea-132">The <xref:System.ServiceModel.ServiceHost> class hosts services and defines several events that may be needed for handling errors.</span></span> <span data-ttu-id="9c6ea-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9c6ea-133">For example:</span></span>  
  
1.  <!--zz <xref:System.ServiceModel.ServiceHost.Faulted>-->  `System.ServiceModel.ServiceHost.Faulted`
  
2. <!--zz  <xref:System.ServiceModel.ServiceHost.UnknownMessageReceived>  --> `System.ServiceModel.ServiceHost.UnknownMessageReceived`
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="9c6ea-134"> <xref:System.ServiceModel.ServiceHost></span><span class="sxs-lookup"><span data-stu-id="9c6ea-134"> <xref:System.ServiceModel.ServiceHost></span></span>
