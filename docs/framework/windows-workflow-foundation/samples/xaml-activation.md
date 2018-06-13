---
title: Attivazione XAML
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517712"
---
# <a name="xaml-activation"></a><span data-ttu-id="fd3a2-102">Attivazione XAML</span><span class="sxs-lookup"><span data-stu-id="fd3a2-102">XAML Activation</span></span>
<span data-ttu-id="fd3a2-103">In questo esempio viene illustrato come ospitare un flusso di lavoro dichiarativo in IIS.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="fd3a2-104">L'esempio è un flusso di lavoro di base chiamato `EchoService` che ha un'operazione.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fd3a2-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fd3a2-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fd3a2-107">Se questa directory non esiste, andare al (pagina di download) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fd3a2-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fd3a2-109">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="fd3a2-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fd3a2-110">Aprire la soluzione XAMLActivation.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd3a2-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="fd3a2-111">Compilare la soluzione premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="fd3a2-112">Eseguire WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="fd3a2-113">Da un prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fd3a2-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="fd3a2-114">cd %SystemDrive%\Programmi\Microsoft Visual Studio 10.0\Common7\IDE\\</span><span class="sxs-lookup"><span data-stu-id="fd3a2-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="fd3a2-115">Eseguire WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="fd3a2-116">Imposta l'indirizzo del servizio su WcfTestClient.exe premendo CTRL + MAIUSC + A e impostando l'indirizzo del servizio su http://localhost:56133/Service.xamlx.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="fd3a2-117">Eseguire l'operazione echo per testare il servizio.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="fd3a2-118">Distribuire il servizio in IIS usando DeployToIIS.Bat in un prompt dei comandi con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="fd3a2-119">Aggiornare l'indirizzo del servizio nel client per http://localhost/XAMLActivation/Service.xamlx e testare il servizio utilizzando WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="fd3a2-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>
