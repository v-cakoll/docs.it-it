---
title: Esposizione dei dati con CacheMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34832f23-e93b-40e6-a80b-606a855a00d9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26c68c24ad525d077d26f0b7bd917a936372e0a5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="exposing-data-with-cachemetadata"></a><span data-ttu-id="376d3-102">Esposizione dei dati con CacheMetadata</span><span class="sxs-lookup"><span data-stu-id="376d3-102">Exposing data with CacheMetadata</span></span>
<span data-ttu-id="376d3-103">Prima di eseguire un'attività, il runtime del flusso di lavoro ottiene tutte le informazioni sull'attività necessarie per la gestione dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="376d3-103">Before executing an activity, the workflow runtime obtains all of the information about the activity that it needs in order to maintain its execution.</span></span> <span data-ttu-id="376d3-104">Tali informazioni vengono ottenute durante l'esecuzione del metodo <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="376d3-104">The workflow runtime gets this information during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="376d3-105">L'implementazione predefinita di questo metodo fornisce al runtime tutti gli argomenti pubblici, le variabili e le attività figlio esposti dall'attività al momento dell'esecuzione; se l'attività deve dare ulteriori informazioni al runtime, ad esempio membri privati o attività che devono essere pianificate dall'attività, è possibile eseguire l'override di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="376d3-105">The default implementation of this method provides the runtime with all of the public arguments, variables, and child activities exposed by the activity at the time it is executed; if the activity needs to give more information to the runtime than this (such as private members, or activities to be scheduled by the activity), this method can be overridden to provide it.</span></span>  
  
## <a name="default-cachemetadata-behavior"></a><span data-ttu-id="376d3-106">Comportamento predefinito di CacheMetadata</span><span class="sxs-lookup"><span data-stu-id="376d3-106">Default CacheMetadata behavior</span></span>  
 <span data-ttu-id="376d3-107">L'implementazione predefinita di <xref:System.Activities.NativeActivity.CacheMetadata%2A> per le attività che derivano da <xref:System.Activities.NativeActivity> elabora i tipi di metodo seguenti nelle modalità riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="376d3-107">The default implementation of <xref:System.Activities.NativeActivity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.NativeActivity> processes the following method types in the following ways:</span></span>  
  
-   <span data-ttu-id="376d3-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> o <xref:System.Activities.InOutArgument%601> (argomenti generici): questi argomenti vengono esposti al runtime come argomenti con nome e tipo uguali al nome e al tipo di proprietà esposti, la direzione di argomento appropriata e alcuni dati di convalida.</span><span class="sxs-lookup"><span data-stu-id="376d3-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, or <xref:System.Activities.InOutArgument%601> (generic arguments): These arguments are exposed to the runtime as arguments with a name and type equal to the exposed property name and type, the appropriate argument direction, and some validation data.</span></span>  
  
-   <span data-ttu-id="376d3-109"><xref:System.Activities.Variable> o qualsiasi sottoclasse relativa: questi membri vengono esposti al runtime come variabili pubbliche.</span><span class="sxs-lookup"><span data-stu-id="376d3-109"><xref:System.Activities.Variable> or any subclass thereof: These members are exposed to the runtime as public variables.</span></span>  
  
-   <span data-ttu-id="376d3-110"><xref:System.Activities.Activity> o qualsiasi sottoclasse relativa: questi membri vengono esposti al runtime come attività figlio pubbliche.</span><span class="sxs-lookup"><span data-stu-id="376d3-110"><xref:System.Activities.Activity> or any subclass thereof: These members are exposed to the runtime as public child activities.</span></span> <span data-ttu-id="376d3-111">Il comportamento predefinito può essere implementato in modo esplicito chiamando <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>, passando nell'attività figlio.</span><span class="sxs-lookup"><span data-stu-id="376d3-111">The default behavior can be implemented explicity by calling <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>, passing in the child activity.</span></span>  
  
-   <span data-ttu-id="376d3-112"><xref:System.Activities.ActivityDelegate> o qualsiasi sottoclasse relativa: questi membri vengono esposti al runtime come delegati pubblici.</span><span class="sxs-lookup"><span data-stu-id="376d3-112"><xref:System.Activities.ActivityDelegate> or any subclass thereof: These members are exposed to the runtime as public delegates.</span></span>  
  
-   <span data-ttu-id="376d3-113"><xref:System.Collections.ICollection> di tipo <xref:System.Activities.Variable>: tutti gli elementi della raccolta vengono esposti al runtime come variabili pubbliche.</span><span class="sxs-lookup"><span data-stu-id="376d3-113"><xref:System.Collections.ICollection> of type <xref:System.Activities.Variable>: All elements in the collection are exposed to the runtime as public variables.</span></span>  
  
-   <span data-ttu-id="376d3-114"><xref:System.Collections.ICollection> di tipo <xref:System.Activities.Activity>: tutti gli elementi della raccolta vengono esposti al runtime come elementi figlio pubblici.</span><span class="sxs-lookup"><span data-stu-id="376d3-114"><xref:System.Collections.ICollection> of type <xref:System.Activities.Activity>: All elements in the collection are exposed to the runtime as public children.</span></span>  
  
-   <span data-ttu-id="376d3-115"><xref:System.Collections.ICollection> di tipo <xref:System.Activities.ActivityDelegate>: tutti gli elementi nella raccolta vengono esposti al runtime come delegati pubblici.</span><span class="sxs-lookup"><span data-stu-id="376d3-115"><xref:System.Collections.ICollection> of type <xref:System.Activities.ActivityDelegate>: All elements in the collection are exposed to the runtime as public delegates.</span></span>  
  
 <span data-ttu-id="376d3-116">Anche l'oggetto <xref:System.Activities.Activity.CacheMetadata%2A> per le attività che derivano da <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity> e <xref:System.Activities.AsyncCodeActivity> funziona nel modo descritto sopra, tranne che per le differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="376d3-116">The <xref:System.Activities.Activity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity>, and <xref:System.Activities.AsyncCodeActivity> also function as above, except for the following differences:</span></span>  
  
-   <span data-ttu-id="376d3-117">Le classi che derivano da <xref:System.Activities.Activity> non possono pianificare attività figlio o delegati, pertanto tali membri vengono esposti come elementi figlio e delegati importati.</span><span class="sxs-lookup"><span data-stu-id="376d3-117">Classes that derive from <xref:System.Activities.Activity> cannot schedule child activities or delegates, so such members are exposed as imported children and delegates; the</span></span>  
  
-   <span data-ttu-id="376d3-118">Le classi che derivano da <xref:System.Activities.CodeActivity> e <xref:System.Activities.AsyncCodeActivity> non supportano variabili, elementi figli o delegati, pertanto vengono esposti solo gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="376d3-118">Classes that derive from <xref:System.Activities.CodeActivity> and <xref:System.Activities.AsyncCodeActivity> do not support variables, children, or delegates, so only arguments will be exposed.</span></span>  
  
## <a name="overriding-cachemetadata-to-provide-information-to-the-runtime"></a><span data-ttu-id="376d3-119">Override di CacheMetadata per fornire informazioni al runtime</span><span class="sxs-lookup"><span data-stu-id="376d3-119">Overriding CacheMetadata to provide information to the runtime</span></span>  
 <span data-ttu-id="376d3-120">Nel frammento di codice seguente viene illustrato come aggiungere informazioni sui membri ai metadati di un'attività durante l'esecuzione del metodo <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="376d3-120">The following code snippet demonstrates how to add information about members to an activity’s metadata during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="376d3-121">Notare che la base del metodo è chiamata per memorizzare nella cache tutti i dati pubblici sull'attività.</span><span class="sxs-lookup"><span data-stu-id="376d3-121">Note that the base of the method is called to cache all public data about the activity.</span></span>  
  
```  
protected override void CacheMetadata(NativeActivityMetadata metadata)  
{      
    base.CacheMetadata(metadata);  
    metadata.AddImplementationChild(this._writeLine);  
    metadata.AddVariable(this._myVariable);  
    metadata.AddImplementationVariable(this._myImplementationVariable);  
  
    RuntimeArgument argument = new RuntimeArgument("MyArgument", ArgumentDirection.In, typeof(SomeType));  
    metadata.Bind(argument, this.SomeName);  
    metadata.AddArgument(argument);  
}  
```  
  
## <a name="using-cachemetadata-to-expose-implementation-children"></a><span data-ttu-id="376d3-122">Uso di CacheMetadata per esporre elementi figlio di implementazione</span><span class="sxs-lookup"><span data-stu-id="376d3-122">Using CacheMetadata to expose implementation children</span></span>  
 <span data-ttu-id="376d3-123">Per passare dati ad attività figlio che devono essere pianificate da un'attività usando variabili, è necessario aggiungere le variabili come variabili di implementazione; i valori delle variabili pubbliche non possono essere impostati in questo modo.</span><span class="sxs-lookup"><span data-stu-id="376d3-123">In order to pass data to child activities that are to be scheduled by an activity using variables, it is necessary to add the variables as implementation variables; public variables cannot have their values set this way.</span></span> <span data-ttu-id="376d3-124">Il motivo di ciò è che le attività devono essere eseguite più come implementazioni di funzioni (che dispongono di parametri) che come classi incapsulate (che dispongono di proprietà).</span><span class="sxs-lookup"><span data-stu-id="376d3-124">The reason for this is that activities are intended to be executed more as implementations of functions (which have parameters), rather than encapsulated classes (which have properties).</span></span> <span data-ttu-id="376d3-125">Tuttavia, ci sono situazioni nelle quali gli argomenti devono essere impostati in modo esplicito, ad esempio nel caso dell'utilizzo di <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, dal momento che l'attività pianificata non dispone dell'accesso agli argomenti dell'attività padre come un'attività figlio.</span><span class="sxs-lookup"><span data-stu-id="376d3-125">However, there are situations in which the arguments must be explicitly set, such as when using <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, since the scheduled activity doesn't have access to the parent activity's arguments in the way a child activity would.</span></span>  
  
 <span data-ttu-id="376d3-126">Nel frammento di codice seguente viene illustrato come passare un argomento da un'attività nativa in un'attività pianificata usando <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="376d3-126">The following code snippet demonstrates how to pass an argument form a native activity into a scheduled activity using <xref:System.Activities.Activity.CacheMetadata%2A>.</span></span>  
  
```  
public sealed class ChildActivity : NativeActivity  
{  
    public WriteLine _writeLine;  
    public InArgument<string> Message { get; set; }  
    private Variable<string> MessageVariable { get; set; }  
    public ChildActivity()  
    {  
        MessageVariable = new Variable<string>();  
        _writeLine = new WriteLine  
        {  
            Text = new InArgument<string>(MessageVariable),  
        };  
    }  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        metadata.AddImplementationVariable(this.MessageVariable);  
        metadata.AddImplementationChild(this._writeLine);  
    }  
    protected override void Execute(NativeActivityContext context)  
    {  
        string configuredMessage = context.GetValue(Message);  
        context.SetValue(MessageVariable, configuredMessage);  
        context.ScheduleActivity(this._writeLine);  
    }  
}  
```
