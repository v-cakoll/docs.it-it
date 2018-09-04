---
title: Utilizzo di base delle attività SendParameters e ReceiveParameters
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: c13999ad1571a6413e30e801b6c642000f8e4654
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504008"
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a><span data-ttu-id="5f731-102">Utilizzo di base delle attività SendParameters e ReceiveParameters</span><span class="sxs-lookup"><span data-stu-id="5f731-102">Basic Usage of SendParameters and ReceiveParameters Activities</span></span>
<span data-ttu-id="5f731-103">Nell'esempio seguente viene illustrato l'uso delle attività <xref:System.ServiceModel.Activities.SendParametersContent> e <xref:System.ServiceModel.Activities.ReceiveParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="5f731-103">This sample shows the use of <xref:System.ServiceModel.Activities.SendParametersContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> activities.</span></span> <span data-ttu-id="5f731-104">Il servizio espone un'operazione che accetta un argomento di tipo stringa e restituisce l'input al client.</span><span class="sxs-lookup"><span data-stu-id="5f731-104">The service exposes one operation that takes a string argument and echoes the input back to the client.</span></span> <span data-ttu-id="5f731-105">Nell'esempio viene illustrato come configurare i parametri per queste attività di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="5f731-105">The sample shows how to set up the parameters for these messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5f731-106">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5f731-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5f731-107">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5f731-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5f731-108">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="5f731-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5f731-109">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="5f731-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a><span data-ttu-id="5f731-110">Utilizzo dell'esempio</span><span class="sxs-lookup"><span data-stu-id="5f731-110">Using this sample</span></span>  
  
1.  <span data-ttu-id="5f731-111">Caricare la soluzione del progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="5f731-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="5f731-112">Eseguire innanzitutto l'applicazione EchoWorkflowService, generata in [directory soluzione di base]\EchoWorkflowService\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="5f731-112">First run the EchoWorkflowService application generated in [solution base directory]\EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="5f731-113">In secondo luogo eseguire l'applicazione EchoWorkflowClient generata in [directory soluzione di base]\EchoWorkflowClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="5f731-113">Second, run the EchoWorkflowClient application generated in [solution base directory]\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="5f731-114">Il client chiama l'operazione Echo nel servizio e stampa i risultati.</span><span class="sxs-lookup"><span data-stu-id="5f731-114">The client calls Echo operation on the service and prints the results.</span></span> <span data-ttu-id="5f731-115">Al termine premere INVIO per uscire dal client e quindi dal servizio.</span><span class="sxs-lookup"><span data-stu-id="5f731-115">When complete, press ENTER to exit the client and then the service.</span></span>