---
title: <ThrowUnobservedTaskExceptions> Elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
ms.openlocfilehash: de5a686bcbd88fc52173b488103f033575623d62
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153815"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="0501e-102">\<ThrowUnobservedTaskExceptions> Elemento</span><span class="sxs-lookup"><span data-stu-id="0501e-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="0501e-103">Specifica se le eccezioni di attività non gestite devono comportare l'arresto di un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0501e-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a><span data-ttu-id="0501e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0501e-104">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0501e-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0501e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0501e-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0501e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0501e-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="0501e-107">Attributes</span></span>  
  
|<span data-ttu-id="0501e-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="0501e-108">Attribute</span></span>|<span data-ttu-id="0501e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0501e-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0501e-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0501e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="0501e-111">Specifica se le eccezioni di attività non gestite devono comportare l'arresto del processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0501e-111">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0501e-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="0501e-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="0501e-113">Valore</span><span class="sxs-lookup"><span data-stu-id="0501e-113">Value</span></span>|<span data-ttu-id="0501e-114">Description</span><span class="sxs-lookup"><span data-stu-id="0501e-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0501e-115">Non termina il processo in esecuzione per un'eccezione di attività non gestita.</span><span class="sxs-lookup"><span data-stu-id="0501e-115">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="0501e-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="0501e-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0501e-117">Termina il processo in esecuzione per un'eccezione di attività non gestita.</span><span class="sxs-lookup"><span data-stu-id="0501e-117">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0501e-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0501e-118">Child Elements</span></span>  
 <span data-ttu-id="0501e-119">No.</span><span class="sxs-lookup"><span data-stu-id="0501e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0501e-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0501e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0501e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0501e-121">Element</span></span>|<span data-ttu-id="0501e-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0501e-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0501e-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0501e-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0501e-124">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0501e-124">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="0501e-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="0501e-125">Remarks</span></span>  
 <span data-ttu-id="0501e-126">Se un'eccezione associata a un oggetto <xref:System.Threading.Tasks.Task> non è stata osservata, non esiste alcuna operazione <xref:System.Threading.Tasks.Task.Wait%2A>, l'elemento padre non è associato, la proprietà <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> non è stata letta e l'eccezione di attività viene considerata non osservata.</span><span class="sxs-lookup"><span data-stu-id="0501e-126">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="0501e-127">Nel .NET Framework 4, per impostazione predefinita, se un oggetto <xref:System.Threading.Tasks.Task> con un'eccezione non osservata viene sottoposta a Garbage Collection, il finalizzatore genera un'eccezione e termina il processo.</span><span class="sxs-lookup"><span data-stu-id="0501e-127">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="0501e-128">L'interruzione del processo è determinata dall'intervallo di Garbage Collection e finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="0501e-128">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="0501e-129">Per semplificare la scrittura di codice asincrono in base alle attività da parte degli sviluppatori, il .NET Framework 4,5 modifica questo comportamento predefinito per le eccezioni non osservate.</span><span class="sxs-lookup"><span data-stu-id="0501e-129">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="0501e-130">Le eccezioni non osservate comportano ancora la generazione dell'evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>, ma, per impostazione predefinita, il processo non viene terminato.</span><span class="sxs-lookup"><span data-stu-id="0501e-130">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="0501e-131">Invece, l'eccezione viene ignorata dopo la generazione dell'evento, indipendentemente dal fatto che l'eccezione venga rilevata da un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="0501e-131">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="0501e-132">Nel .NET Framework 4,5, è possibile usare l' [ \<ThrowUnobservedTaskExceptions> elemento](throwunobservedtaskexceptions-element.md) in un file di configurazione dell'applicazione per abilitare il comportamento .NET Framework 4 della generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0501e-132">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="0501e-133">Il comportamento dell'eccezione può anche essere specificato in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0501e-133">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="0501e-134">Impostando la variabile di ambiente `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="0501e-134">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="0501e-135">Impostando il valore DWORD del registro di sistema ThrowUnobservedTaskExceptions = 1 nell'HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft \\ . Chiave di NETFramework.</span><span class="sxs-lookup"><span data-stu-id="0501e-135">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0501e-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="0501e-136">Example</span></span>  
 <span data-ttu-id="0501e-137">Nell'esempio seguente viene illustrato come abilitare la generazione di eccezioni nelle attività tramite un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0501e-137">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="0501e-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="0501e-138">Example</span></span>  
 <span data-ttu-id="0501e-139">Nell'esempio seguente viene illustrata la modalità di generazione di un'eccezione non osservata da parte di un'attività.</span><span class="sxs-lookup"><span data-stu-id="0501e-139">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="0501e-140">Il codice deve essere eseguito come programma rilasciato per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="0501e-140">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0501e-141">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0501e-141">See also</span></span>

- [<span data-ttu-id="0501e-142">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0501e-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0501e-143">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0501e-143">Configuration File Schema</span></span>](../index.md)
