---
title: Esempio di compensazione personalizzata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2bc76267cf4b3fe5f4e792ee185733e51185872f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="custom-compensation-sample"></a><span data-ttu-id="08c26-102">Esempio di compensazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="08c26-102">Custom Compensation Sample</span></span>
<span data-ttu-id="08c26-103">In questo esempio viene illustrato come usare <xref:System.Activities.Statements.CompensableActivity> e il relativo gestore di compensazione per definire la logica di compensazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="08c26-103">This sample shows how to use <xref:System.Activities.Statements.CompensableActivity> and its compensation handler to define custom compensation logic.</span></span> <span data-ttu-id="08c26-104">Lo scenario modellato in questo esempio è una Agenzia di noleggio furgoni.</span><span class="sxs-lookup"><span data-stu-id="08c26-104">The scenario modeled in this sample is a Truck Rental Agency.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="08c26-105">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="08c26-105">Sample Details</span></span>  
 <span data-ttu-id="08c26-106">Di seguito sono riportati i passaggi simulati:</span><span class="sxs-lookup"><span data-stu-id="08c26-106">The steps simulated are:</span></span>  
  
1.  <span data-ttu-id="08c26-107">L'utente richiede preventivi per il noleggio di furgoni per una data specificata.</span><span class="sxs-lookup"><span data-stu-id="08c26-107">The user requests truck rental quotes for a given date.</span></span>  
  
2.  <span data-ttu-id="08c26-108">Vengono contattate tre società di noleggio furgoni e vengono forniti tre preventivi.</span><span class="sxs-lookup"><span data-stu-id="08c26-108">Three truck companies are contacted and the three quotes are provided.</span></span>  
  
3.  <span data-ttu-id="08c26-109">L'utente sceglie un preventivo e procede all'ordine tramite carta di credito.</span><span class="sxs-lookup"><span data-stu-id="08c26-109">The user selects one truck quote and proceeds to order by credit card.</span></span>  
  
4.  <span data-ttu-id="08c26-110">Gli altri due preventivi vengono annullati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="08c26-110">The application cancels the other two truck quotes.</span></span>  
  
5.  <span data-ttu-id="08c26-111">Tramite l'applicazione viene addebitata una commissione di servizio che non è risarcibile, per i clienti privi di un conto premium, se l'annullamento avviene entro un massimo di 10 giorni antecedenti la data di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="08c26-111">The application charges a service fee that is non-refundable for non-premium accounts if cancelation happens 10 days or less prior to the reservation date.</span></span>  
  
6.  <span data-ttu-id="08c26-112">Tramite l'applicazione viene addebitata la tariffa di noleggio del furgone.</span><span class="sxs-lookup"><span data-stu-id="08c26-112">The application charges the truck rental fee.</span></span>  
  
7.  <span data-ttu-id="08c26-113">L'applicazione attende fino alla data di prenotazione o fino a quando il cliente decide di annullare la prenotazione, a seconda dell'evento che si verifica per primo.</span><span class="sxs-lookup"><span data-stu-id="08c26-113">The application waits until the reservation date or until the customer decided to cancel the reservation, whichever comes first.</span></span>  
  
8.  <span data-ttu-id="08c26-114">Se il cliente annulla la prenotazione, viene eseguita la logica di compensazione personalizzata <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> in base alla logica seguente:</span><span class="sxs-lookup"><span data-stu-id="08c26-114">If the customer cancels the reservation, the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> custom compensation logic runs according to the following logic:</span></span>  
  
    1.  <span data-ttu-id="08c26-115">Se il cliente non dispone di un conto "premium" e mancano meno di 10 giorni alla data di prenotazione, la commissione di servizio viene comunque addebitata. In caso contrario, la commissione di servizio viene rimborsata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="08c26-115">If the customer has a non-premium account and it is less than 10 days prior to the reservation date, then the service fee is still charged; otherwise, the application refunds the service fee.</span></span>  
  
    2.  <span data-ttu-id="08c26-116">Il resto delle attività compensabili (ordine del furgone + tariffa di ordine del furgone) viene eseguito sulla base della logica di compensazione predefinita che consiste nel compensare in ordine inverso di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="08c26-116">The rest of the compensable activities (truck order + truck order fee) are run according to the default compensation logic, which is to compensate in reverse order of execution.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="08c26-117">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="08c26-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="08c26-118">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione CustomCompensation.sln.</span><span class="sxs-lookup"><span data-stu-id="08c26-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CustomCompensation.sln solution.</span></span> <span data-ttu-id="08c26-119">Si trova nella directory \WF\Basic\Compensation\CustomCompensation.</span><span class="sxs-lookup"><span data-stu-id="08c26-119">It is located in the \WF\Basic\Compensation\CustomCompensation directory.</span></span>  
  
2.  <span data-ttu-id="08c26-120">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="08c26-120">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="08c26-121">Premere CTRL+F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="08c26-121">Press CTRL + F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="08c26-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="08c26-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="08c26-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="08c26-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="08c26-124">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08c26-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="08c26-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="08c26-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`