---
title: Attivazione XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f513b10c84de968d5a18b800037b512aad90399e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-activation"></a><span data-ttu-id="b8a4a-102">Attivazione XAML</span><span class="sxs-lookup"><span data-stu-id="b8a4a-102">XAML Activation</span></span>
<span data-ttu-id="b8a4a-103">In questo esempio viene illustrato come ospitare un flusso di lavoro dichiarativo in IIS.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="b8a4a-104">L'esempio è un flusso di lavoro di base chiamato `EchoService` che ha un'operazione.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b8a4a-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b8a4a-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b8a4a-107">Se questa directory non esiste, visitare la pagina di download per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8a4a-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b8a4a-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b8a4a-109">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b8a4a-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b8a4a-110">Aprire la soluzione XAMLActivation.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8a4a-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="b8a4a-111">Compilare la soluzione premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="b8a4a-112">Eseguire WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="b8a4a-113">Da un prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b8a4a-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="b8a4a-114">cd %SystemDrive%\Programmi\Microsoft Visual Studio 10.0\Common7\IDE\\</span><span class="sxs-lookup"><span data-stu-id="b8a4a-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="b8a4a-115">Eseguire WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="b8a4a-116">Impostare l'indirizzo del servizio su WcfTestClient.exe premendo CTRL+MAIUSC+A e impostando l'indirizzo del servizio su http://localhost:56133/Service.xamlx.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="b8a4a-117">Eseguire l'operazione echo per testare il servizio.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="b8a4a-118">Distribuire il servizio in IIS usando DeployToIIS.Bat in un prompt dei comandi con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="b8a4a-119">Aggiornare l'indirizzo del servizio nel client modificandolo in http://localhost/XAMLActivation/Service.xamlx e testare di nuovo il servizio usando WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="b8a4a-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>
