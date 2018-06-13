---
title: Invio e gestione di errori
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 6796b4daccd88adc3bd006f454ce96ca155fbcb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516126"
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="bf68c-102">Invio e gestione di errori</span><span class="sxs-lookup"><span data-stu-id="bf68c-102">Sending and Handling Faults</span></span>
<span data-ttu-id="bf68c-103">In questo esempio viene illustrato come usare le attività di messaggistica <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply> per inviare e ricevere errori previsti e imprevisti.</span><span class="sxs-lookup"><span data-stu-id="bf68c-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="bf68c-104">In questo scenario, la prima richiesta del client comporta un errore previsto incluso nella raccolta <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf68c-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="bf68c-105">Le successive richieste del client comportano la ricezione di errori imprevisti, prima del completamento della richiesta finale.</span><span class="sxs-lookup"><span data-stu-id="bf68c-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="bf68c-106">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="bf68c-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="bf68c-107">Aprire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni elevate facendo clic con il [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="bf68c-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="bf68c-108">Aprire il file della soluzione Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="bf68c-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="bf68c-109">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="bf68c-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="bf68c-110">Eseguire il progetto del servizio.</span><span class="sxs-lookup"><span data-stu-id="bf68c-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="bf68c-111">In **Esplora**, fare doppio clic su di `FaultService` del progetto e selezionare **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="bf68c-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="bf68c-112">Premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="bf68c-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="bf68c-113">Aprire un'altra copia del [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni elevate facendo clic con il [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="bf68c-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="bf68c-114">Aprire il file della soluzione Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="bf68c-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="bf68c-115">Eseguire il progetto del client.</span><span class="sxs-lookup"><span data-stu-id="bf68c-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="bf68c-116">In **Esplora**, fare doppio clic su di `FaultClient` del progetto e selezionare **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="bf68c-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="bf68c-117">Premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="bf68c-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf68c-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="bf68c-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bf68c-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="bf68c-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bf68c-120">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="bf68c-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bf68c-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="bf68c-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`