---
title: '&lt;ThrowUnobservedTaskExceptions&gt; elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f72bedbaaf0b15ade7ff6b7b8c3edcdfd3fda6d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749426"
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a><span data-ttu-id="19aac-102">&lt;ThrowUnobservedTaskExceptions&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="19aac-102">&lt;ThrowUnobservedTaskExceptions&gt; Element</span></span>
<span data-ttu-id="19aac-103">Specifica se le eccezioni di attività non gestite devono comportare l'arresto di un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="19aac-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="19aac-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="19aac-104">\<configuration></span></span>  
<span data-ttu-id="19aac-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="19aac-105">\<runtime></span></span>  
<span data-ttu-id="19aac-106">\<ThrowUnobservedTaskExceptions ></span><span class="sxs-lookup"><span data-stu-id="19aac-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19aac-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19aac-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19aac-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="19aac-108">Attributes and Elements</span></span>  
 <span data-ttu-id="19aac-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="19aac-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19aac-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="19aac-110">Attributes</span></span>  
  
|<span data-ttu-id="19aac-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="19aac-111">Attribute</span></span>|<span data-ttu-id="19aac-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19aac-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="19aac-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="19aac-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="19aac-114">Specifica se le eccezioni di attività non gestite devono comportare l'arresto del processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="19aac-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="19aac-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="19aac-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="19aac-116">Valore</span><span class="sxs-lookup"><span data-stu-id="19aac-116">Value</span></span>|<span data-ttu-id="19aac-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19aac-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="19aac-118">Non termina il processo in esecuzione per un'eccezione di attività non gestita.</span><span class="sxs-lookup"><span data-stu-id="19aac-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="19aac-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="19aac-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="19aac-120">Termina il processo in esecuzione per un'eccezione di attività non gestita.</span><span class="sxs-lookup"><span data-stu-id="19aac-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19aac-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="19aac-121">Child Elements</span></span>  
 <span data-ttu-id="19aac-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="19aac-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19aac-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="19aac-123">Parent Elements</span></span>  
  
|<span data-ttu-id="19aac-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="19aac-124">Element</span></span>|<span data-ttu-id="19aac-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19aac-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="19aac-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19aac-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="19aac-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="19aac-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="19aac-128">Note</span><span class="sxs-lookup"><span data-stu-id="19aac-128">Remarks</span></span>  
 <span data-ttu-id="19aac-129">Se un'eccezione associata a un oggetto <xref:System.Threading.Tasks.Task> non è stata osservata, non esiste alcuna operazione <xref:System.Threading.Tasks.Task.Wait%2A>, l'elemento padre non è associato, la proprietà <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> non è stata letta e l'eccezione di attività viene considerata non osservata.</span><span class="sxs-lookup"><span data-stu-id="19aac-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="19aac-130">In [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], per impostazione predefinita, se un oggetto <xref:System.Threading.Tasks.Task> con un'eccezione non osservata viene sottoposto a Garbage Collection, tramite il finalizzatore viene generata un'eccezione e il processo viene terminato.</span><span class="sxs-lookup"><span data-stu-id="19aac-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="19aac-131">L'interruzione del processo è determinata dall'intervallo di Garbage Collection e finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="19aac-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="19aac-132">Per semplificare la scrittura di codice asincrono basato sulle attività per gli sviluppatori, in [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] questo comportamento predefinito viene modificato per le eccezioni non osservate.</span><span class="sxs-lookup"><span data-stu-id="19aac-132">To make it easier for developers to write asynchronous code based on tasks, the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="19aac-133">Le eccezioni non osservate comportano ancora la generazione dell'evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>, ma, per impostazione predefinita, il processo non viene terminato.</span><span class="sxs-lookup"><span data-stu-id="19aac-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="19aac-134">Invece, l'eccezione viene ignorata dopo la generazione dell'evento, indipendentemente dal fatto che l'eccezione venga rilevata da un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="19aac-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="19aac-135">Nel [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], è possibile utilizzare il [ \<ThrowUnobservedTaskExceptions > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in un file di configurazione dell'applicazione per abilitare il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] comportamento di generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="19aac-135">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], you can use the [\<ThrowUnobservedTaskExceptions> element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in an application configuration file to enable the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="19aac-136">Il comportamento dell'eccezione può anche essere specificato in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="19aac-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
-   <span data-ttu-id="19aac-137">Impostando la variabile di ambiente `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="19aac-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
-   <span data-ttu-id="19aac-138">Tramite l'impostazione del Registro di sistema DWORD valore ThrowUnobservedTaskExceptions = 1 nel HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework chiave.</span><span class="sxs-lookup"><span data-stu-id="19aac-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19aac-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="19aac-139">Example</span></span>  
 <span data-ttu-id="19aac-140">Nell'esempio seguente viene illustrato come abilitare la generazione di eccezioni nelle attività tramite un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="19aac-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="19aac-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="19aac-141">Example</span></span>  
 <span data-ttu-id="19aac-142">Nell'esempio seguente viene illustrata la modalità di generazione di un'eccezione non osservata da parte di un'attività.</span><span class="sxs-lookup"><span data-stu-id="19aac-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="19aac-143">Il codice deve essere eseguito come programma rilasciato per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="19aac-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="19aac-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19aac-144">See Also</span></span>  
 [<span data-ttu-id="19aac-145">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="19aac-145">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="19aac-146">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="19aac-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
