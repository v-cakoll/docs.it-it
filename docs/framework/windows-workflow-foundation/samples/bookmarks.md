---
title: Bookmarks2
ms.date: 03/30/2017
ms.assetid: 035fadb2-49fa-4ac7-b398-daf138f66e87
ms.openlocfilehash: 61abc1d1a5084018511975e27fa96311c168eb69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514160"
---
# <a name="bookmarks"></a><span data-ttu-id="44986-102">Segnalibri</span><span class="sxs-lookup"><span data-stu-id="44986-102">Bookmarks</span></span>
<span data-ttu-id="44986-103">In questo esempio viene illustrato come scrivere un'attività personalizzata che crea un segnalibro per ricevere input esterno.</span><span class="sxs-lookup"><span data-stu-id="44986-103">This sample demonstrates how to write a custom activity that creates a bookmark to receive external input.</span></span> <span data-ttu-id="44986-104">L'esempio include anche un'applicazione console di base che usa l'attività personalizzata in un flusso di lavoro e mostra come individuare e riprendere segnalibri associati a un'istanza del flusso di lavoro in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44986-104">The sample also includes a basic console application that uses the custom activity in a workflow and shows how to discover and resume bookmarks associated with a running workflow instance.</span></span> <span data-ttu-id="44986-105">Per altre informazioni sui segnalibri, vedere [segnalibri](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="44986-105">For more information about bookmarks, see [Bookmarks](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="44986-106">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="44986-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="44986-107">Aprire la soluzione di esempio Bookmarks.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44986-107">Open the Bookmarks.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="44986-108">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="44986-108">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="44986-109">Per eseguire il servizio, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="44986-109">To run the sample, press CTRLl + F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44986-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="44986-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="44986-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="44986-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="44986-112">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="44986-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="44986-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="44986-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CodeBodied\Bookmarks`