---
title: "Utilizzo di base delle attività SendParameters e ReceiveParameters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a45e04c4368406255736312503e19de95ed12150
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a><span data-ttu-id="5a309-102">Utilizzo di base delle attività SendParameters e ReceiveParameters</span><span class="sxs-lookup"><span data-stu-id="5a309-102">Basic Usage of SendParameters and ReceiveParameters Activities</span></span>
<span data-ttu-id="5a309-103">Nell'esempio seguente viene illustrato l'uso delle attività <xref:System.ServiceModel.Activities.SendParametersContent> e <xref:System.ServiceModel.Activities.ReceiveParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="5a309-103">This sample shows the use of <xref:System.ServiceModel.Activities.SendParametersContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> activities.</span></span> <span data-ttu-id="5a309-104">Il servizio espone un'operazione che accetta un argomento di tipo stringa e restituisce l'input al client.</span><span class="sxs-lookup"><span data-stu-id="5a309-104">The service exposes one operation that takes a string argument and echoes the input back to the client.</span></span> <span data-ttu-id="5a309-105">Nell'esempio viene illustrato come configurare i parametri per queste attività di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="5a309-105">The sample shows how to set up the parameters for these messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5a309-106">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5a309-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5a309-107">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5a309-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5a309-108">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a309-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5a309-109">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="5a309-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a><span data-ttu-id="5a309-110">Utilizzo dell'esempio</span><span class="sxs-lookup"><span data-stu-id="5a309-110">Using this sample</span></span>  
  
1.  <span data-ttu-id="5a309-111">Caricare la soluzione del progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="5a309-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="5a309-112">Eseguire innanzitutto l'applicazione EchoWorkflowService, generata in [directory soluzione di base]\EchoWorkflowService\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="5a309-112">First run the EchoWorkflowService application generated in [solution base directory]\EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="5a309-113">In secondo luogo eseguire l'applicazione EchoWorkflowClient generata in [directory soluzione di base]\EchoWorkflowClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="5a309-113">Second, run the EchoWorkflowClient application generated in [solution base directory]\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="5a309-114">Il client chiama l'operazione Echo nel servizio e stampa i risultati.</span><span class="sxs-lookup"><span data-stu-id="5a309-114">The client calls Echo operation on the service and prints the results.</span></span> <span data-ttu-id="5a309-115">Al termine premere INVIO per uscire dal client e quindi dal servizio.</span><span class="sxs-lookup"><span data-stu-id="5a309-115">When complete, press ENTER to exit the client and then the service.</span></span>