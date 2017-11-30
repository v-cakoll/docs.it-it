---
title: Formattazione di messaggi nei servizi flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d2367f4fe4ebe576eb9a5e2f707eb043e5ee7ccb
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="3c083-102">Formattazione di messaggi nei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3c083-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="3c083-103">In questo esempio viene illustrato come tipi utente diversi possono essere usati nelle attività di messaggistica (servizi WF).</span><span class="sxs-lookup"><span data-stu-id="3c083-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="3c083-104">Il servizio di esempio è un semplice servizio di approvazione spese ed espone tre operazioni.</span><span class="sxs-lookup"><span data-stu-id="3c083-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="3c083-105">`ApproveExpense` accetta un tipo di contratto dati e mostra come usare i tipi noti.</span><span class="sxs-lookup"><span data-stu-id="3c083-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="3c083-106">L'operazione restituisce `true` o `false` in base all'ammontare della spesa.</span><span class="sxs-lookup"><span data-stu-id="3c083-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="3c083-107">`ApprovePO`accetta un tipo XmlSerializer e restituisce `true` o `false` in base all'ammontare della spesa.`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="3c083-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="3c083-108">accetta un tipo di contratto di messaggio e restituisce `true` o `false` se il fornitore è presente nell'elenco dei fornitori approvati o se la richiesta proviene dal reparto finanziario (il reparto finanziario può usare qualsiasi fornitore).</span><span class="sxs-lookup"><span data-stu-id="3c083-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3c083-109">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="3c083-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="3c083-110">Caricare la soluzione del progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="3c083-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="3c083-111">Eseguire innanzitutto il servizio, generato in [directory soluzione di base]FormatterService\bin\debug\.</span><span class="sxs-lookup"><span data-stu-id="3c083-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="3c083-112">Eseguire quindi l'applicazione Client, generata in [directory soluzione di base]\FormatterClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="3c083-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="3c083-113">Il client chiama tre operazioni nel servizio e stampa i risultati.</span><span class="sxs-lookup"><span data-stu-id="3c083-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="3c083-114">Al termine premere INVIO per uscire dal client e quindi dal servizio.</span><span class="sxs-lookup"><span data-stu-id="3c083-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c083-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3c083-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3c083-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3c083-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3c083-117">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c083-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3c083-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3c083-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`