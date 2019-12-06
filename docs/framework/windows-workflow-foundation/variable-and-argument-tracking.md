---
title: Rilevamento di variabili e argomenti
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: c5d3fe6626c22184edd83de6aedad8589ab2ef35
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837545"
---
# <a name="variable-and-argument-tracking"></a><span data-ttu-id="d5c59-102">Rilevamento di variabili e argomenti</span><span class="sxs-lookup"><span data-stu-id="d5c59-102">Variable and Argument Tracking</span></span>
<span data-ttu-id="d5c59-103">Quando si rileva l'esecuzione di un flusso di lavoro, spesso è utile estrarre i dati.</span><span class="sxs-lookup"><span data-stu-id="d5c59-103">When tracking the execution of a workflow, it is often useful to extract data.</span></span> <span data-ttu-id="d5c59-104">Tali dati offrono un contesto aggiuntivo quando si accede alla post-esecuzione di un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="d5c59-104">This provides additional context when accessing a tracking record post execution.</span></span> <span data-ttu-id="d5c59-105">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], usando il rilevamento, è possibile estrarre qualsiasi variabile o argomento visibile all'interno dell'ambito di tutte le attività di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d5c59-105">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], you can extract any visible variable or argument within the scope of any activity in a workflow using tracking.</span></span> <span data-ttu-id="d5c59-106">I profili di rilevamento semplificano l'estrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d5c59-106">Tracking profiles make it easy to extract data.</span></span>  
  
## <a name="variables-and-arguments"></a><span data-ttu-id="d5c59-107">Variabili e argomenti</span><span class="sxs-lookup"><span data-stu-id="d5c59-107">Variables and Arguments</span></span>  
 <span data-ttu-id="d5c59-108">Le variabili e gli argomenti vengono estratti quando un'attività crea un oggetto ActivityStateRecord.</span><span class="sxs-lookup"><span data-stu-id="d5c59-108">Variables and arguments are extracted when an activity emits an ActivityStateRecord.</span></span>  <span data-ttu-id="d5c59-109">Una variabile può essere estratta solo se è inclusa nell'ambito dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d5c59-109">A variable is available for extraction only if it is within the scope of the activity.</span></span> <span data-ttu-id="d5c59-110">Una variabile da estrarre in un'attività viene specificata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d5c59-110">A variable to be extracted within an activity is specified in the following manner:</span></span>  
  
- <span data-ttu-id="d5c59-111">Se una variabile viene specificata con il relativo nome, il rilevamento cerca la variabile all'interno dell'attività in fase di rilevamento e nelle attività padre.</span><span class="sxs-lookup"><span data-stu-id="d5c59-111">If a variable is specified by the variable name, then tracking looks for the variable within the current activity being tracked and in parent activities.</span></span> <span data-ttu-id="d5c59-112">La variabile viene ricercata nell'ambito dell'attività corrente e nell'ambito padre.</span><span class="sxs-lookup"><span data-stu-id="d5c59-112">The variable is searched in current activity scope and in parent scope.</span></span>  
  
- <span data-ttu-id="d5c59-113">Se le variabili da estrarre vengono specificate usando Name = "\*", vengono estratte tutte le variabili all'interno dell'attività corrente che viene rilevata.</span><span class="sxs-lookup"><span data-stu-id="d5c59-113">If variables to be extracted are specified by using name="\*", then all variables within the current activity being tracked are extracted.</span></span> <span data-ttu-id="d5c59-114">In questo caso, le variabili incluse nell'ambito ma definite nelle attività padre non vengono estratte.</span><span class="sxs-lookup"><span data-stu-id="d5c59-114">In this case variables that are in scope but defined in parent activities are not extracted.</span></span>  
  
 <span data-ttu-id="d5c59-115">Gli argomenti estratti dipendono dallo stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d5c59-115">When extracting arguments, the arguments extracted depend on the state of the activity.</span></span> <span data-ttu-id="d5c59-116">Quando lo stato di un'attività è Executing, possono essere estratti solo gli argomenti `InArguments`.</span><span class="sxs-lookup"><span data-stu-id="d5c59-116">When the state of an activity is Executing, then only the `InArguments` are available for extraction.</span></span> <span data-ttu-id="d5c59-117">Per qualsiasi altro stato dell'attività (Closed, Faulted, Canceled), entrambi gli argomenti InArguments e OutArguments sono disponibili per l'estrazione.</span><span class="sxs-lookup"><span data-stu-id="d5c59-117">For any other activity state (Closed, Faulted, Canceled), all arguments, both InArguments and OutArguments, are available for extraction.</span></span>  
  
 <span data-ttu-id="d5c59-118">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d5c59-118">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d5c59-119">Le variabili e gli argomenti possono essere estratti solo con un oggetto <xref:System.Activities.Tracking.ActivityStateRecord>, pertanto vengono sottoscritti all'interno di un profilo di rilevamento tramite l'oggetto <xref:System.Activities.Tracking.ActivityStateQuery>.</span><span class="sxs-lookup"><span data-stu-id="d5c59-119">Variables and arguments can be extracted only with an <xref:System.Activities.Tracking.ActivityStateRecord> and thus are subscribed to within a tracking profile using <xref:System.Activities.Tracking.ActivityStateQuery>.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a><span data-ttu-id="d5c59-120">Protezione delle informazioni archiviate in variabili e argomenti</span><span class="sxs-lookup"><span data-stu-id="d5c59-120">Protecting Information Stored Within Variables and Arguments</span></span>  
 <span data-ttu-id="d5c59-121">Una variabile o un argomento rilevato viene reso visibile per impostazione predefinita dal runtime di WF.</span><span class="sxs-lookup"><span data-stu-id="d5c59-121">A tracked variable or argument is by default made visible by the WF runtime.</span></span> <span data-ttu-id="d5c59-122">Uno sviluppatore di flussi di lavoro può limitarne l'accesso eseguendo i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d5c59-122">A workflow developer can protect it from being accessed by taking the following steps:</span></span>  
  
1. <span data-ttu-id="d5c59-123">Crittografia del valore di una variabile.</span><span class="sxs-lookup"><span data-stu-id="d5c59-123">Encrypt the value of a variable.</span></span>  
  
2. <span data-ttu-id="d5c59-124">Controllo della creazione di un profilo di rilevamento per impedire l'estrazione di una variabile o di un argomento.</span><span class="sxs-lookup"><span data-stu-id="d5c59-124">Control the authoring of a tracking profile to prevent the extraction of a variable or argument.</span></span>  
  
3. <span data-ttu-id="d5c59-125">Per i partecipanti del rilevamento personalizzato, assicurarsi che il codice di WF non diffonda informazioni riservate archiviate nelle variabili o negli argomenti.</span><span class="sxs-lookup"><span data-stu-id="d5c59-125">For custom tracking participants ensure that the WF code does not disclose sensitive information that is stored in variables or arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c59-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5c59-126">See also</span></span>

- <span data-ttu-id="d5c59-127">[Monitoraggio di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d5c59-127">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="d5c59-128">[Monitoraggio delle applicazioni con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d5c59-128">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
