---
title: "Utilizzo di attività procedurali"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c391316959829c77d16dd87af51d9fe1915dc88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-procedural-activities"></a><span data-ttu-id="74b91-102">Utilizzo di attività procedurali</span><span class="sxs-lookup"><span data-stu-id="74b91-102">Using Procedural Activities</span></span>
<span data-ttu-id="74b91-103">Nell'esempio vengono usate le attività <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>e <xref:System.Activities.Statements.WriteLine> per implementare un gioco per indovinare un numero.</span><span class="sxs-lookup"><span data-stu-id="74b91-103">The sample uses the <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, and <xref:System.Activities.Statements.WriteLine> activities to implement a guessing game.</span></span> <span data-ttu-id="74b91-104">Il gioco seleziona un numero casuale e il giocatore deve indovinare il numero.</span><span class="sxs-lookup"><span data-stu-id="74b91-104">The guessing game selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="74b91-105">Quando il giocatore invia un numero errato, il flusso di lavoro fornisce un suggerimento che indica di provare a con un numero più alto o più basso.</span><span class="sxs-lookup"><span data-stu-id="74b91-105">When the player submits an incorrect guess, the workflow provides a hint whether to guess higher or lower.</span></span> <span data-ttu-id="74b91-106">Se il giocatore indovina il numero in meno di 7 tentativi, viene visualizzato all'utente un messaggio di congratulazioni speciali.</span><span class="sxs-lookup"><span data-stu-id="74b91-106">If the player guesses the number in less than 7 attempts, a special congratulations is displayed to the user.</span></span>  
  
## <a name="custom-activities-in-this-sample"></a><span data-ttu-id="74b91-107">Attività personalizzate in questo esempio</span><span class="sxs-lookup"><span data-stu-id="74b91-107">Custom Activities in this Sample</span></span>  
  
### <a name="readline"></a><span data-ttu-id="74b91-108">ReadLine</span><span class="sxs-lookup"><span data-stu-id="74b91-108">ReadLine</span></span>  
 <span data-ttu-id="74b91-109">Legge una riga di testo dalla console.</span><span class="sxs-lookup"><span data-stu-id="74b91-109">Reads a line of text from the console.</span></span> <span data-ttu-id="74b91-110">Questa attività deriva dalla classe <xref:System.Activities.NativeActivity> e crea un segnalibro ripreso dall'applicazione console quando viene letta una riga.</span><span class="sxs-lookup"><span data-stu-id="74b91-110">This activity derives from the <xref:System.Activities.NativeActivity> class and creates a bookmark that is resumed by the console application when a line is read.</span></span>  
  
### <a name="promptint"></a><span data-ttu-id="74b91-111">PromptInt</span><span class="sxs-lookup"><span data-stu-id="74b91-111">PromptInt</span></span>  
 <span data-ttu-id="74b91-112">Richiede all'utente di digitare un numero, quindi lo legge da una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="74b91-112">Prompts the user to type in a number and then reads it from a console window.</span></span> <span data-ttu-id="74b91-113">L'attività deriva da <xref:System.Activities.Activity%601> e usa le attività <xref:System.Activities.Statements.WriteLine> e `ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="74b91-113">The activity derives from <xref:System.Activities.Activity%601> and uses the <xref:System.Activities.Statements.WriteLine> and `ReadLine` activities.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="74b91-114">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="74b91-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="74b91-115">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione GuessingGame.sln.</span><span class="sxs-lookup"><span data-stu-id="74b91-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the GuessingGame.sln solution file.</span></span>  
  
2.  <span data-ttu-id="74b91-116">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="74b91-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="74b91-117">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="74b91-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74b91-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="74b91-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="74b91-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="74b91-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="74b91-120">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74b91-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="74b91-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="74b91-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## <a name="see-also"></a><span data-ttu-id="74b91-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74b91-122">See Also</span></span>
