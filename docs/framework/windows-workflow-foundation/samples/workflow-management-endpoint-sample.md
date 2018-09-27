---
title: Esempio di endpoint di gestione del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: 398ace1c198f0db0268c44083ccc98c5ba2d2c7f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399125"
---
# <a name="workflow-management-endpoint-sample"></a><span data-ttu-id="0545f-102">Esempio di endpoint di gestione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0545f-102">Workflow Management Endpoint Sample</span></span>
<span data-ttu-id="0545f-103">In questo esempio viene illustrato come è possibile usare un endpoint di controllo del flusso di lavoro per creare ed eseguire flussi di lavoro sia in modalità locale che remota.</span><span class="sxs-lookup"><span data-stu-id="0545f-103">This sample shows how a workflow control endpoint can be used to create and run workflows both locally and remotely.</span></span> <span data-ttu-id="0545f-104">Nell'esempio viene illustrato come ospitare un endpoint di controllo e scrivere client che chiamano l'endpoint di controllo per creare ed eseguire l'istanza di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0545f-104">The sample demonstrates how to host a control endpoint and write clients that call the control endpoint to create and run the instance of a workflow.</span></span> <span data-ttu-id="0545f-105">Il flusso di lavoro non è un servizio.</span><span class="sxs-lookup"><span data-stu-id="0545f-105">The workflow is not a service.</span></span>  
  
 <span data-ttu-id="0545f-106">Sul lato del servizio nell'esempio un flusso di lavoro è ospitato con l'oggetto WorkflowServiceHost e viene aggiunto un oggetto WorkflowControlEndpoint in modo da consentire ai client di eseguire le operazioni di controllo (sospensione, avvio e via di seguito).</span><span class="sxs-lookup"><span data-stu-id="0545f-106">On the service side of the sample a workflow is hosted with WorkflowServiceHost and a WorkflowControlEndpoint is added so that clients can perform control operations (Suspend, Start, etc).</span></span> <span data-ttu-id="0545f-107">Viene inoltre aggiunto un oggetto CreationEndpoint definito dall'utente per consentire la creazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0545f-107">A user-defined CreationEndpoint is also added to allow the workflow to be created.</span></span> <span data-ttu-id="0545f-108">Il servizio usa quindi questi endpoint per avviare il flusso di lavoro in uno stato sospeso per poi riprenderne l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0545f-108">The service then uses these endpoints to start the workflow in a suspended state and then resume the workflow.</span></span> <span data-ttu-id="0545f-109">Il client esegue le stesse operazioni ma dal codice client.</span><span class="sxs-lookup"><span data-stu-id="0545f-109">The client performs the same operations but from the client code.</span></span> <span data-ttu-id="0545f-110">Per altre informazioni su queste interfacce, vedere [Endpoint di controllo del flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="0545f-110">For more information about these interfaces see, [Workflow Control Endpoint](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md).</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="0545f-111">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0545f-111">To run the sample</span></span>  
  
1.  <span data-ttu-id="0545f-112">Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0545f-112">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="0545f-113">Aprire la soluzione di esempio ManagementEndpoint.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0545f-113">Open the ManagementEndpoint.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="0545f-114">Per compilare la soluzione, premere CTRL + MAIUSC + B o scegliere **Compila soluzione** dalle **compilazione** menu.</span><span class="sxs-lookup"><span data-stu-id="0545f-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
4.  <span data-ttu-id="0545f-115">Avviare l'applicazione ManagementEndpoint.exe.</span><span class="sxs-lookup"><span data-stu-id="0545f-115">Start the ManagementEndpoint.exe application.</span></span>  
  
5.  <span data-ttu-id="0545f-116">Avviare l'applicazione Client.exe.</span><span class="sxs-lookup"><span data-stu-id="0545f-116">Start the Client.exe application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0545f-117">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0545f-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0545f-118">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0545f-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0545f-119">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="0545f-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0545f-120">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0545f-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`