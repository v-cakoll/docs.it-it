---
title: Determinazione della durata dell'operazione del servizio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c96aa6752feca637f89ed309d1a5c87cea4a3a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="determining-service-operation-duration"></a><span data-ttu-id="25b46-102">Determinazione della durata dell'operazione del servizio</span><span class="sxs-lookup"><span data-stu-id="25b46-102">Determining service operation duration</span></span>
<span data-ttu-id="25b46-103">Se la traccia analitica è abilitata in un'applicazione [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], la durata di esecuzione per un'operazione del servizio può essere determinata con facilità esaminando il registro eventi.</span><span class="sxs-lookup"><span data-stu-id="25b46-103">If analytic tracing is enabled in a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] application, the duration of execution for a service operation can easily be determined by examining the event log.</span></span>  <span data-ttu-id="25b46-104">In questo argomento viene descritto come determinare la quantità di tempo richiesta per il completamento di un'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="25b46-104">This topic demonstrates how to determine the amount of time a service operation takes to complete.</span></span>  
  
### <a name="determining-service-operation-execution-duration"></a><span data-ttu-id="25b46-105">Determinazione della durata di esecuzione dell'operazione del servizio</span><span class="sxs-lookup"><span data-stu-id="25b46-105">Determining service operation execution duration</span></span>  
  
1.  <span data-ttu-id="25b46-106">Aprire il Visualizzatore eventi fare clic su **avviare**, **eseguire**e l'immissione di `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="25b46-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="25b46-107">Se è stata abilitata la traccia analitica, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="25b46-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="25b46-108">Selezionare **vista**, **Mostra analitica e registri di Debug**.</span><span class="sxs-lookup"><span data-stu-id="25b46-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="25b46-109">Fare doppio clic su **analitico** e selezionare **Attiva registro**.</span><span class="sxs-lookup"><span data-stu-id="25b46-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="25b46-110">Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce dopo l'esecuzione dell'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="25b46-110">Leave Event Viewer open so that traces can be viewed after the service operation is run.</span></span>  
  
3.  <span data-ttu-id="25b46-111">Aprire quindi un'applicazione [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in cui siano inclusi un progetto di servizio e un progetto client che interagisce con tale servizio.</span><span class="sxs-lookup"><span data-stu-id="25b46-111">Next, open a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] application that includes a service project and a client project that interacts with that service.</span></span>  <span data-ttu-id="25b46-112">È possibile creare un'applicazione di questo tipo seguendo il [esercitazione introduttiva](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="25b46-112">You can create such an application by following the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  <span data-ttu-id="25b46-113">Se si dispone di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] gli esempi installati, è possibile aprire il [Introduzione](../../../../../docs/framework/wcf/samples/getting-started-sample.md), che contiene il progetto completato, creato nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="25b46-113">If you have the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="25b46-114">Eseguire l'applicazione server premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="25b46-114">Execute the server application by pressing **F5**.</span></span> <span data-ttu-id="25b46-115">Eseguire l'applicazione client facendo clic su di **Client** progetto, quindi selezionando **Debug**, **Avvia nuova istanza**.</span><span class="sxs-lookup"><span data-stu-id="25b46-115">Execute the client application by right-clicking on the **Client** project and selecting **Debug**, **Start New Instance**.</span></span>  
  
5.  <span data-ttu-id="25b46-116">Nel Visualizzatore eventi aggiornare il registro analitico e ordinare gli eventi in base all'ID evento.</span><span class="sxs-lookup"><span data-stu-id="25b46-116">In Event Viewer, refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="25b46-117">Ricercare gli eventi con ID evento [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span><span class="sxs-lookup"><span data-stu-id="25b46-117">Look for events with Event ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span></span>  <span data-ttu-id="25b46-118">Questi eventi indicheranno le operazioni completate, nonché la relativa durata.</span><span class="sxs-lookup"><span data-stu-id="25b46-118">These events will show which operations have completed, and what the duration of the operation was.</span></span>  <span data-ttu-id="25b46-119">L'evento seguente indica la durata di un'operazione Add.</span><span class="sxs-lookup"><span data-stu-id="25b46-119">The following event shows the duration of an Add operation.</span></span>  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
