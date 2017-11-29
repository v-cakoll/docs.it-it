---
title: Calcolatrice correlata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9d0d3c03b946a1f3805ea6e229e4019540b58286
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="correlated-calculator"></a><span data-ttu-id="6d8c9-102">Calcolatrice correlata</span><span class="sxs-lookup"><span data-stu-id="6d8c9-102">Correlated Calculator</span></span>
<span data-ttu-id="6d8c9-103">In questo esempio viene illustrato come usare le attività di messaggistica (<xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>) nella finestra di progettazione con correlazione basata sul contenuto in base a un parametro nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-103">This sample demonstrates how to use the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>) in the designer with content-based correlation based on a parameter in the message.</span></span> <span data-ttu-id="6d8c9-104">In questo scenario, le operazioni della calcolatrice sono in una serie di istruzioni parallele.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-104">In this scenario, the operations of the calculator are in a parallel convoy.</span></span> <span data-ttu-id="6d8c9-105">Sia un'istanza sia una correlazione (basate su `CalculatorId`) vengono create quando viene inviato il primo messaggio al flusso di lavoro mentre i messaggi successivi con lo stesso `CalculatorId` vengono inviati a tale istanza fino a quando non viene chiamata l'operazione di reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-105">Both an instance and a correlation (based on `CalculatorId`) are created when the first message is sent to the workflow, and subsequent messages with the same `CalculatorId` are dispatched to that instance until the Reset operation is called.</span></span> <span data-ttu-id="6d8c9-106">Il client viene implementato come applicazione WPF che usa un proxy client basato su codice per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-106">The client is implemented as a WPF application that uses a code-based client proxy to communicate with the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6d8c9-107">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="6d8c9-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="6d8c9-108">Avviare [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] nelle autorizzazioni elevate e aprire il file della soluzione For.sln.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-108">Start [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in elevated permissions, open the For.sln solution file.</span></span>  
  
    1.  <span data-ttu-id="6d8c9-109">Passare alla cartella che contiene [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d8c9-109">Navigate to the folder that contains [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    2.  <span data-ttu-id="6d8c9-110">Fare doppio clic su Devenv.exe e selezionare **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-110">Right-click Devenv.exe and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="6d8c9-111">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione CorrelatedCalculator.sln.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CorrelatedCalculator.sln solution file.</span></span>  
  
3.  <span data-ttu-id="6d8c9-112">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="6d8c9-113">Per eseguire il progetto servizio, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-113">To run the service project, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="6d8c9-114">Una volta che servizio è pronto e in attesa dei messaggi, in Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto Client ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-114">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d8c9-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6d8c9-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6d8c9-117">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d8c9-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6d8c9-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6d8c9-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`  
  
## <a name="see-also"></a><span data-ttu-id="6d8c9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d8c9-119">See Also</span></span>
