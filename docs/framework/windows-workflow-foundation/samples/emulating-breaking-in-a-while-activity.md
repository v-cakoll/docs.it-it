---
title: Emulazione di interruzione in un'attività While
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 27264832dd82719d7ccb81e1398df343653515b1
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="emulating-breaking-in-a-while-activity"></a><span data-ttu-id="635c0-102">Emulazione di interruzione in un'attività While</span><span class="sxs-lookup"><span data-stu-id="635c0-102">Emulating breaking in a While activity</span></span>
<span data-ttu-id="635c0-103">In questo esempio viene illustrato come interrompere il meccanismo di ciclo delle attività seguenti: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While> e <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="635c0-103">This sample demonstrates how to break the looping mechanism of the following activities: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>  
  
 <span data-ttu-id="635c0-104">Ciò è utile perché Windows Workflow Foundation (WF) non è inclusa alcuna attività per interrompere l'esecuzione di questi cicli.</span><span class="sxs-lookup"><span data-stu-id="635c0-104">This is useful because Windows Workflow Foundation (WF) does not include any activity to break the execution of these loops.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="635c0-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="635c0-105">Scenario</span></span>  
 <span data-ttu-id="635c0-106">Nell'esempio viene rilevato il primo fornitore affidabile in un elenco di fornitori (istanze della classe `Vendor`).</span><span class="sxs-lookup"><span data-stu-id="635c0-106">The sample finds the first reliable vendor from a list of vendors (instances of the `Vendor` class).</span></span> <span data-ttu-id="635c0-107">Ogni fornitore dispone di un oggetto `ID`, di un oggetto `Name` e di un valore di affidabilità numerico che determina l'affidabilità del fornitore.</span><span class="sxs-lookup"><span data-stu-id="635c0-107">Each vendor has an `ID`, a `Name` and a numeric reliability value that determines how dependable the vendor is.</span></span> <span data-ttu-id="635c0-108">Nell'esempio viene creata un'attività personalizzata denominata `FindReliableVendor` che riceve due parametri di input (un elenco di fornitori e un valore di affidabilità minimo) e restituisce il primo fornitore dell'elenco che corrisponde ai criteri forniti.</span><span class="sxs-lookup"><span data-stu-id="635c0-108">The sample creates a custom activity called `FindReliableVendor` that receives two input parameters (a list of vendors and a minimum reliability value) and returns the first vendor of the list that matches the supplied criteria.</span></span>  
  
## <a name="breaking-a-loop"></a><span data-ttu-id="635c0-109">Interruzione di un ciclo</span><span class="sxs-lookup"><span data-stu-id="635c0-109">Breaking a Loop</span></span>  
 <span data-ttu-id="635c0-110">Windows Workflow Foundation (WF) non include un'attività per interrompere un ciclo.</span><span class="sxs-lookup"><span data-stu-id="635c0-110">Windows Workflow Foundation (WF) does not include an activity to break a loop.</span></span> <span data-ttu-id="635c0-111">Nell'esempio di codice viene eseguita l'interruzione di un ciclo tramite un'attività <xref:System.Activities.Statements.If> e diverse variabili.</span><span class="sxs-lookup"><span data-stu-id="635c0-111">The code sample accomplishes breaking a loop by using an <xref:System.Activities.Statements.If> activity and several variables.</span></span> <span data-ttu-id="635c0-112">Nell'esempio, l'attività <xref:System.Activities.Statements.While> viene interrotta dopo che alla variabile `reliableVendor` viene assegnato un valore diverso da `null`.</span><span class="sxs-lookup"><span data-stu-id="635c0-112">In the sample, the <xref:System.Activities.Statements.While> activity is broken once the `reliableVendor` variable is assigned a value other than `null`.</span></span>  
  
 <span data-ttu-id="635c0-113">Nell'esempio di codice seguente viene illustrato il modo in cui l'esempio interrompe un ciclo while.</span><span class="sxs-lookup"><span data-stu-id="635c0-113">The following code example demonstrates how the sample breaks a while loop.</span></span>  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="635c0-114">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="635c0-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="635c0-115">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione EmulatingBreakInWhile.sln.</span><span class="sxs-lookup"><span data-stu-id="635c0-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EmulatingBreakInWhile.sln solution file.</span></span>  
  
2.  <span data-ttu-id="635c0-116">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="635c0-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="635c0-117">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="635c0-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="635c0-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="635c0-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="635c0-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="635c0-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="635c0-120">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="635c0-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="635c0-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="635c0-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`