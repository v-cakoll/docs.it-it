---
title: Formattazione di messaggi nei servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
ms.openlocfilehash: eac9f7042dbcbd31f9a8c7d5e56c7b7d2ab62156
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513786"
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="64d68-102">Formattazione di messaggi nei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="64d68-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="64d68-103">In questo esempio viene illustrato come tipi utente diversi possono essere usati nelle attività di messaggistica (servizi WF).</span><span class="sxs-lookup"><span data-stu-id="64d68-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="64d68-104">Il servizio di esempio è un semplice servizio di approvazione spese ed espone tre operazioni.</span><span class="sxs-lookup"><span data-stu-id="64d68-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="64d68-105">`ApproveExpense` accetta un tipo di contratto dati e mostra come usare i tipi noti.</span><span class="sxs-lookup"><span data-stu-id="64d68-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="64d68-106">L'operazione restituisce `true` o `false` in base all'ammontare della spesa.</span><span class="sxs-lookup"><span data-stu-id="64d68-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="64d68-107">`ApprovePO` accetta un tipo XmlSerializer e restituisce `true` o `false` in base all'ammontare della spesa.`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="64d68-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="64d68-108">accetta un tipo di contratto di messaggio e restituisce `true` o `false` se il fornitore è presente nell'elenco dei fornitori approvati o se la richiesta proviene dal reparto finanziario (il reparto finanziario può usare qualsiasi fornitore).</span><span class="sxs-lookup"><span data-stu-id="64d68-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="64d68-109">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="64d68-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="64d68-110">Caricare la soluzione del progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="64d68-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="64d68-111">Eseguire innanzitutto il servizio, generato in [directory soluzione di base]FormatterService\bin\debug\.</span><span class="sxs-lookup"><span data-stu-id="64d68-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="64d68-112">Eseguire quindi l'applicazione Client, generata in [directory soluzione di base]\FormatterClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="64d68-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="64d68-113">Il client chiama tre operazioni nel servizio e stampa i risultati.</span><span class="sxs-lookup"><span data-stu-id="64d68-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="64d68-114">Al termine premere INVIO per uscire dal client e quindi dal servizio.</span><span class="sxs-lookup"><span data-stu-id="64d68-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64d68-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="64d68-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="64d68-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="64d68-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="64d68-117">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="64d68-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="64d68-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="64d68-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`