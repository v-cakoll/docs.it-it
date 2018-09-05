---
title: Caricare da XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: 3344f8d35400835ed022ba507954f7f962ff75c8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43745434"
---
# <a name="load-from-xaml"></a><span data-ttu-id="6484f-102">Caricare da XAML</span><span class="sxs-lookup"><span data-stu-id="6484f-102">Load From XAML</span></span>
<span data-ttu-id="6484f-103">In questo esempio viene illustrato come caricare dinamicamente un flusso di lavoro XAML senza dovere eseguire lo strumento XamlBuildTask.</span><span class="sxs-lookup"><span data-stu-id="6484f-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="6484f-104">Nell'esempio viene chiamato il metodo <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="6484f-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="6484f-105">L'esempio è un'applicazione client Windows Presentation Foundation (WPF) che carica flussi di lavoro XAML usando il <xref:System.Activities.XamlIntegration.ActivityXamlServices> classe e li esegue.</span><span class="sxs-lookup"><span data-stu-id="6484f-105">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="6484f-106">Dopo essere stati caricati usando la classe <xref:System.Activities.XamlIntegration.ActivityXamlServices>, viene restituito un oggetto <xref:System.Activities.DynamicActivity%601> che può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="6484f-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6484f-107">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="6484f-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="6484f-108">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione LoadFromXAML.sln.</span><span class="sxs-lookup"><span data-stu-id="6484f-108">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LoadFromXAML.sln solution file.</span></span>  
  
2.  <span data-ttu-id="6484f-109">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="6484f-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6484f-110">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="6484f-110">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6484f-111">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6484f-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6484f-112">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6484f-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6484f-113">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="6484f-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6484f-114">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6484f-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`