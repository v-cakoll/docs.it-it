---
title: Calcolatrice correlata
ms.date: 03/30/2017
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
ms.openlocfilehash: 77e13b3ca913d2432cfe5d4a95e83764effbb109
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514141"
---
# <a name="correlated-calculator"></a><span data-ttu-id="8b35e-102">Calcolatrice correlata</span><span class="sxs-lookup"><span data-stu-id="8b35e-102">Correlated Calculator</span></span>
<span data-ttu-id="8b35e-103">In questo esempio viene illustrato come usare le attività di messaggistica (<xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>) nella finestra di progettazione con correlazione basata sul contenuto in base a un parametro nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="8b35e-103">This sample demonstrates how to use the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>) in the designer with content-based correlation based on a parameter in the message.</span></span> <span data-ttu-id="8b35e-104">In questo scenario, le operazioni della calcolatrice sono in una serie di istruzioni parallele.</span><span class="sxs-lookup"><span data-stu-id="8b35e-104">In this scenario, the operations of the calculator are in a parallel convoy.</span></span> <span data-ttu-id="8b35e-105">Sia un'istanza sia una correlazione (basate su `CalculatorId`) vengono create quando viene inviato il primo messaggio al flusso di lavoro mentre i messaggi successivi con lo stesso `CalculatorId` vengono inviati a tale istanza fino a quando non viene chiamata l'operazione di reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="8b35e-105">Both an instance and a correlation (based on `CalculatorId`) are created when the first message is sent to the workflow, and subsequent messages with the same `CalculatorId` are dispatched to that instance until the Reset operation is called.</span></span> <span data-ttu-id="8b35e-106">Il client viene implementato come applicazione WPF che usa un proxy client basato su codice per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="8b35e-106">The client is implemented as a WPF application that uses a code-based client proxy to communicate with the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="8b35e-107">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="8b35e-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="8b35e-108">Avviare [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] nelle autorizzazioni elevate e aprire il file della soluzione For.sln.</span><span class="sxs-lookup"><span data-stu-id="8b35e-108">Start [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in elevated permissions, open the For.sln solution file.</span></span>  
  
    1.  <span data-ttu-id="8b35e-109">Passare alla cartella che contiene [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b35e-109">Navigate to the folder that contains [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    2.  <span data-ttu-id="8b35e-110">Fare doppio clic su Devenv.exe e selezionare **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="8b35e-110">Right-click Devenv.exe and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="8b35e-111">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione CorrelatedCalculator.sln.</span><span class="sxs-lookup"><span data-stu-id="8b35e-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CorrelatedCalculator.sln solution file.</span></span>  
  
3.  <span data-ttu-id="8b35e-112">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="8b35e-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="8b35e-113">Per eseguire il progetto servizio, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="8b35e-113">To run the service project, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="8b35e-114">Una volta che servizio è pronto e in attesa dei messaggi, in Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto Client ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="8b35e-114">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b35e-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="8b35e-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8b35e-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="8b35e-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8b35e-117">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="8b35e-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8b35e-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="8b35e-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`