---
title: Comunicazione asincrona
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: b5cf788ce4587dacb5a7642e25cb1b5b1e6f3e3c
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044370"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="38631-102">Comunicazione asincrona</span><span class="sxs-lookup"><span data-stu-id="38631-102">Asynchronous Communication</span></span>
<span data-ttu-id="38631-103">In questo esempio viene illustrato come la comunicazione tra due diversi servizi di Windows Workflow Foundation (WF) viene eseguita in modo asincrono per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="38631-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="38631-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="38631-104">Demonstrates</span></span>  
 <span data-ttu-id="38631-105">Comunicazione asincronica tra servizi [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38631-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="38631-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="38631-106">Discussion</span></span>  
 <span data-ttu-id="38631-107">In questo esempio viene illustrata la modalità di esecuzione della comunicazione asincrona tra applicazioni [!INCLUDE[wf1](../../../../includes/wf1-md.md)] tramite le attività di messaggistica fornite da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38631-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="38631-108">L'esempio è costituito dai tre progetti seguenti.</span><span class="sxs-lookup"><span data-stu-id="38631-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="38631-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="38631-109">CreditCheckService</span></span>  
 <span data-ttu-id="38631-110">Questo servizio riceve il punteggio del credito di una particolare persona o il valore dell'elemento da acquisire, quindi stabilisce se viene concesso alla persona il credito.</span><span class="sxs-lookup"><span data-stu-id="38631-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="38631-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="38631-111">RentalApprovalService</span></span>  
 <span data-ttu-id="38631-112">Questo servizio riceve un'applicazione da una persona che richiede credito.</span><span class="sxs-lookup"><span data-stu-id="38631-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="38631-113">Il servizio comunica in modo asincrono con `CreditCheckService` per determinare se la richiesta di credito è valida.</span><span class="sxs-lookup"><span data-stu-id="38631-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="38631-114">Client</span><span class="sxs-lookup"><span data-stu-id="38631-114">Client</span></span>  
 <span data-ttu-id="38631-115">Il client comunica in modo sincrono con `RentalApprovalService` per sapere se il credito è approvato.</span><span class="sxs-lookup"><span data-stu-id="38631-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="38631-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="38631-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="38631-117">Fare clic con il pulsante destro del mouse sulla soluzione **AsynchronousCommunication** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="38631-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="38631-118">In **Proprietà comuni**selezionare **progetto di avvio**e selezionare **progetti di avvio multipli**.</span><span class="sxs-lookup"><span data-stu-id="38631-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="38631-119">Spostare **RentalApprovalService** nella prima posizione dell'elenco, seguito da **CreditCheckService**, seguito da **client**.</span><span class="sxs-lookup"><span data-stu-id="38631-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="38631-120">Impostare l'azione di **avvio** su tutti e tre i progetti.</span><span class="sxs-lookup"><span data-stu-id="38631-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="38631-121">Fare clic su **OK**e premere F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="38631-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="38631-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="38631-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="38631-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="38631-123">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="38631-124">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi.</span><span class="sxs-lookup"><span data-stu-id="38631-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="38631-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="38631-125">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
