---
title: Guida introduttiva alla scrittura di un'attività personalizzata
ms.date: 03/30/2017
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
ms.openlocfilehash: 4d9c140ca230750ca1119b33252b1edb8796d458
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43776658"
---
# <a name="getting-started-writing-a-custom-activity"></a><span data-ttu-id="bbe85-102">Guida introduttiva alla scrittura di un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="bbe85-102">Getting Started Writing a Custom Activity</span></span>
<span data-ttu-id="bbe85-103">In questo esempio viene illustrato come definire una semplice attività personalizzata in XAML.</span><span class="sxs-lookup"><span data-stu-id="bbe85-103">This sample demonstrates how to define a simple custom activity in XAML.</span></span> <span data-ttu-id="bbe85-104">All'attività viene assegnato il nome `Rhyme` e la relativa logica è una sequenza di tre attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="bbe85-104">The activity is given the name `Rhyme`, and its logic is a sequence of three <xref:System.Activities.Statements.WriteLine> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bbe85-105">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="bbe85-105">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bbe85-106">Aprire il **sln** nella soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbe85-106">Open the **Simple.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="bbe85-107">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="bbe85-107">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bbe85-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="bbe85-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bbe85-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="bbe85-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bbe85-110">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="bbe85-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bbe85-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="bbe85-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`