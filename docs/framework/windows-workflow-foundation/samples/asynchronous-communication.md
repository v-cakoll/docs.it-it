---
title: Comunicazione asincrona
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1b9435342d73fc5cb292ee72781362146604ce9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-communication"></a><span data-ttu-id="098de-102">Comunicazione asincrona</span><span class="sxs-lookup"><span data-stu-id="098de-102">Asynchronous Communication</span></span>
<span data-ttu-id="098de-103">In questo esempio viene illustrata la modalità di esecuzione della comunicazione, eseguita in modo asincrono per impostazione predefinita, tra due diversi servizi [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="098de-103">This sample demonstrates how the communication between two different [!INCLUDE[wf](../../../../includes/wf-md.md)] services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="098de-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="098de-104">Demonstrates</span></span>  
 <span data-ttu-id="098de-105">Comunicazione asincronica tra servizi [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="098de-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="098de-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="098de-106">Discussion</span></span>  
 <span data-ttu-id="098de-107">In questo esempio viene illustrata la modalità di esecuzione della comunicazione asincrona tra applicazioni [!INCLUDE[wf1](../../../../includes/wf1-md.md)] tramite le attività di messaggistica fornite da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="098de-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="098de-108">L'esempio è costituito dai tre progetti seguenti.</span><span class="sxs-lookup"><span data-stu-id="098de-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="098de-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="098de-109">CreditCheckService</span></span>  
 <span data-ttu-id="098de-110">Questo servizio riceve il punteggio del credito di una particolare persona o il valore dell'elemento da acquisire, quindi stabilisce se viene concesso alla persona il credito.</span><span class="sxs-lookup"><span data-stu-id="098de-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="098de-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="098de-111">RentalApprovalService</span></span>  
 <span data-ttu-id="098de-112">Questo servizio riceve un'applicazione da una persona che richiede credito.</span><span class="sxs-lookup"><span data-stu-id="098de-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="098de-113">Il servizio comunica in modo asincrono con `CreditCheckService` per determinare se la richiesta di credito è valida.</span><span class="sxs-lookup"><span data-stu-id="098de-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="098de-114">Client</span><span class="sxs-lookup"><span data-stu-id="098de-114">Client</span></span>  
 <span data-ttu-id="098de-115">Il client comunica in modo sincrono con `RentalApprovalService` per sapere se il credito è approvato.</span><span class="sxs-lookup"><span data-stu-id="098de-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="098de-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="098de-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="098de-117">Fare doppio clic su di **AsynchronousCommunication** soluzioni e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="098de-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="098de-118">In **proprietà comuni**selezionare **progetto di avvio**e selezionare **più progetti di avvio**.</span><span class="sxs-lookup"><span data-stu-id="098de-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="098de-119">Spostare **RentalApprovalService** nella prima posizione nell'elenco, seguito da **CreditCheckService**, seguito da **Client**.</span><span class="sxs-lookup"><span data-stu-id="098de-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="098de-120">Impostare il **avviare** azione in tutti e tre i progetti.</span><span class="sxs-lookup"><span data-stu-id="098de-120">Set the **Start** action on all three projects.</span></span>  
  
4.  <span data-ttu-id="098de-121">Fare clic su **OK**, premere F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="098de-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="098de-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="098de-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="098de-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="098de-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="098de-124">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="098de-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="098de-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="098de-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
