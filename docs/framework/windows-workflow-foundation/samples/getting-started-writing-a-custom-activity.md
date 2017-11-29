---
title: "Guida introduttiva alla scrittura di un'attività personalizzata"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4921f9f2dbfb8405019a5bc0c0b8242ea66f2db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="7171c-102">Guida introduttiva alla scrittura di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="7171c-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="7171c-103">In questo esempio viene illustrato come definire una semplice attività personalizzata in XAML.</span><span class="sxs-lookup"><span data-stu-id="7171c-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="7171c-104">All'attività viene assegnato il nome `Rhyme` e la relativa logica è una sequenza di tre attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="7171c-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7171c-105">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="7171c-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7171c-106">Aprire il **Simple.sln** soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7171c-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="7171c-107">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="7171c-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7171c-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="7171c-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7171c-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="7171c-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7171c-110">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7171c-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7171c-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="7171c-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`  
  
## <a name="see-also"></a><span data-ttu-id="7171c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7171c-112">See Also</span></span>
