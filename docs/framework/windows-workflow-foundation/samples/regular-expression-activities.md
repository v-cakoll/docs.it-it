---
title: Attività di espressioni regolari
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74aef126011789cfd48aa962973cc67a4132c224
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="regular-expression-activities"></a><span data-ttu-id="d5906-102">Attività di espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="d5906-102">Regular Expression Activities</span></span>
<span data-ttu-id="d5906-103">In questo esempio viene illustrato come creare un set di attività che espongono la funzionalità delle espressioni regolari dello spazio dei nomi <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="d5906-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="d5906-104">Queste attività personalizzate possono essere usate all'interno di un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d5906-104">These custom activities can be used within a workflow application.</span></span> <span data-ttu-id="d5906-105">Per ulteriori informazioni sulle espressioni regolari, vedere [n: System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span><span class="sxs-lookup"><span data-stu-id="d5906-105">For more information about regular expressions, see [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="d5906-106">Nella tabella seguente sono indicate in dettaglio le attività personalizzate in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d5906-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="d5906-107">Attività</span><span class="sxs-lookup"><span data-stu-id="d5906-107">Activity</span></span>|<span data-ttu-id="d5906-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5906-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d5906-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="d5906-109">IsMatch</span></span>|<span data-ttu-id="d5906-110">Specifica se l'espressione regolare ha trovato una corrispondenza nella stringa di input.</span><span class="sxs-lookup"><span data-stu-id="d5906-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="d5906-111">Corrispondenze</span><span class="sxs-lookup"><span data-stu-id="d5906-111">Matches</span></span>|<span data-ttu-id="d5906-112">Cerca una stringa di input di tutte le occorrenze di un'espressione regolare e restituisce tutte le corrispondenze esatte.</span><span class="sxs-lookup"><span data-stu-id="d5906-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="d5906-113">Sostituisci</span><span class="sxs-lookup"><span data-stu-id="d5906-113">Replace</span></span>|<span data-ttu-id="d5906-114">All'interno di una stringa di input specificata, sostituisce le stringhe che corrispondono ai criteri di ricerca dell'espressione regolare con una stringa di sostituzione specificata.</span><span class="sxs-lookup"><span data-stu-id="d5906-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="d5906-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="d5906-115">IsMatch</span></span>  
 <span data-ttu-id="d5906-116">L'attività personalizzata `IsMatch` restituisce `true` se la proprietà della stringa di `Input` trova una corrispondenza nell'espressione regolare specificata nella proprietà `Pattern`.</span><span class="sxs-lookup"><span data-stu-id="d5906-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="d5906-117">L'attività deriva da <xref:System.Activities.CodeActivity%601> e all'interno del metodo <xref:System.Activities.CodeActivity%601.Execute%2A> chiama il metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5906-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="d5906-118">Nella tabella seguente vengono descritte le proprietà e il valore restituito per l'attività personalizzata `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="d5906-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="d5906-119">Proprietà o valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5906-119">Property or Return Value</span></span>|<span data-ttu-id="d5906-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5906-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="d5906-121">Pattern (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="d5906-121">Pattern (required)</span></span>|<span data-ttu-id="d5906-122">Espressione regolare con cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d5906-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="d5906-123">Input (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="d5906-123">Input (required)</span></span>|<span data-ttu-id="d5906-124">Stringa di input da cercare.</span><span class="sxs-lookup"><span data-stu-id="d5906-124">The input string to search.</span></span>|  
|<span data-ttu-id="d5906-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="d5906-125">RegexOptions</span></span>|<span data-ttu-id="d5906-126">Combinazione OR bit per bit di [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d5906-126">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="d5906-127">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5906-127">Return value</span></span>|<span data-ttu-id="d5906-128">`true` se l'input trova una corrispondenza nel criterio di ricerca specificato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d5906-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="d5906-129">Nell'esempio di codice riportato di seguito viene illustrato come usare l'attività personalizzata `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="d5906-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="d5906-130">Corrispondenze</span><span class="sxs-lookup"><span data-stu-id="d5906-130">Matches</span></span>  
 <span data-ttu-id="d5906-131">L'attività personalizzata `Matches` cerca una stringa di input di tutte le occorrenze di un'espressione regolare e restituisce tutte le corrispondenze esatte.</span><span class="sxs-lookup"><span data-stu-id="d5906-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="d5906-132">L'attività deriva da <xref:System.Activities.CodeActivity%601> e all'interno del metodo <xref:System.Activities.CodeActivity%601.Execute%2A> chiama il metodo <xref:System.Text.RegularExpressions.Regex.Matches%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5906-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="d5906-133">Nella tabella seguente vengono descritte le proprietà e il valore restituito per l'attività personalizzata `IsMatch`.</span><span class="sxs-lookup"><span data-stu-id="d5906-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="d5906-134">Proprietà o valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5906-134">Property or Return Value</span></span>|<span data-ttu-id="d5906-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5906-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="d5906-136">Pattern (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="d5906-136">Pattern (required)</span></span>|<span data-ttu-id="d5906-137">Espressione regolare con cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d5906-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="d5906-138">Input (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="d5906-138">Input (required)</span></span>|<span data-ttu-id="d5906-139">Stringa di input da cercare.</span><span class="sxs-lookup"><span data-stu-id="d5906-139">The input string to search.</span></span>|  
|<span data-ttu-id="d5906-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="d5906-140">RegexOptions</span></span>|<span data-ttu-id="d5906-141">Combinazione OR bit per bit di [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d5906-141">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="d5906-142">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5906-142">Return Value</span></span>|<span data-ttu-id="d5906-143">Oggetto <xref:System.Text.RegularExpressions.MatchCollection> che contiene la raccolta di corrispondenze esatte.</span><span class="sxs-lookup"><span data-stu-id="d5906-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="d5906-144">Nell'esempio di codice riportato di seguito viene illustrato come usare l'attività personalizzata `Matches`.</span><span class="sxs-lookup"><span data-stu-id="d5906-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="d5906-145">Sostituisci</span><span class="sxs-lookup"><span data-stu-id="d5906-145">Replace</span></span>  
 <span data-ttu-id="d5906-146">L'attività personalizzata `Replace` cerca una stringa di input e sostituisce tutte le stringhe che corrispondono a un'espressione regolare specificata con una stringa.</span><span class="sxs-lookup"><span data-stu-id="d5906-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="d5906-147">L'attività deriva da <xref:System.Activities.CodeActivity%601> e all'interno del metodo <xref:System.Activities.CodeActivity%601.Execute%2A> chiama il metodo <xref:System.Text.RegularExpressions.Regex.Replace%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5906-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="d5906-148">Nella tabella seguente vengono descritte le proprietà e il valore restituito per l'attività personalizzata `Replace`.</span><span class="sxs-lookup"><span data-stu-id="d5906-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="d5906-149">Proprietà o valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5906-149">Property or Return Value</span></span>|<span data-ttu-id="d5906-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5906-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="d5906-151">Pattern (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="d5906-151">Pattern (required)</span></span>|<span data-ttu-id="d5906-152">Espressione regolare con cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d5906-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="d5906-153">Input (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="d5906-153">Input (required)</span></span>|<span data-ttu-id="d5906-154">Stringa di input da cercare.</span><span class="sxs-lookup"><span data-stu-id="d5906-154">The input string to search.</span></span>|  
|<span data-ttu-id="d5906-155">Replacement</span><span class="sxs-lookup"><span data-stu-id="d5906-155">Replacement</span></span>|<span data-ttu-id="d5906-156">Stringa di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="d5906-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="d5906-157">Se viene specificato `Replacement`, la proprietà `MatchEvaluator` viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="d5906-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="d5906-158">Deve essere impostata la proprietà `Replacement` o `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="d5906-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="d5906-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="d5906-159">MatchEvaluator</span></span>|<span data-ttu-id="d5906-160">Metodo personalizzato che esamina ogni corrispondenza e restituisce la stringa corrispondente originale o una stringa di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="d5906-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="d5906-161">Se viene specificato `Replacement`, la proprietà `MatchEvaluator` viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="d5906-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="d5906-162">Deve essere impostata la proprietà `Replacement` o `MatchEvaluator`.</span><span class="sxs-lookup"><span data-stu-id="d5906-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="d5906-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="d5906-163">RegexOptions</span></span>|<span data-ttu-id="d5906-164">Combinazione OR bit per bit di [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d5906-164">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="d5906-165">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5906-165">Return Value</span></span>|<span data-ttu-id="d5906-166">Oggetto <xref:System.Text.RegularExpressions.MatchCollection> che contiene la raccolta di corrispondenze esatte.</span><span class="sxs-lookup"><span data-stu-id="d5906-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="d5906-167">Nell'esempio di codice riportato di seguito viene illustrato come usare l'attività personalizzata `Replace`.</span><span class="sxs-lookup"><span data-stu-id="d5906-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d5906-168">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="d5906-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="d5906-169">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione RegexActivities.sln.</span><span class="sxs-lookup"><span data-stu-id="d5906-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d5906-170">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="d5906-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d5906-171">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="d5906-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5906-172">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d5906-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d5906-173">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d5906-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d5906-174">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5906-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d5906-175">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d5906-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`