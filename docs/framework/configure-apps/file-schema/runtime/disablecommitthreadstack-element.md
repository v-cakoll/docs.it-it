---
title: <disableCommitThreadStack> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: 8aefb8a20d6a95c5b8062d0c03dcb28a3557ca3d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117467"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="93129-102">\<disableCommitThreadStack> Elemento</span><span class="sxs-lookup"><span data-stu-id="93129-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="93129-103">Specifica se viene eseguito il commit dello stack di thread completo quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="93129-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a><span data-ttu-id="93129-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93129-104">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93129-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="93129-105">Attributes and Elements</span></span>  
 <span data-ttu-id="93129-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="93129-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93129-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="93129-107">Attributes</span></span>  
  
|<span data-ttu-id="93129-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="93129-108">Attribute</span></span>|<span data-ttu-id="93129-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93129-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93129-110">Enabled</span><span class="sxs-lookup"><span data-stu-id="93129-110">enabled</span></span>|<span data-ttu-id="93129-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="93129-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="93129-112">Specifica se il commit dello stack di thread completo all'avvio del thread (comportamento predefinito) è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="93129-112">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="93129-113">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="93129-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="93129-114">Valore</span><span class="sxs-lookup"><span data-stu-id="93129-114">Value</span></span>|<span data-ttu-id="93129-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93129-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93129-116">0</span><span class="sxs-lookup"><span data-stu-id="93129-116">0</span></span>|<span data-ttu-id="93129-117">Non disabilitare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="93129-117">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="93129-118">1</span><span class="sxs-lookup"><span data-stu-id="93129-118">1</span></span>|<span data-ttu-id="93129-119">Disattivare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="93129-119">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93129-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="93129-120">Child Elements</span></span>  
 <span data-ttu-id="93129-121">No.</span><span class="sxs-lookup"><span data-stu-id="93129-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93129-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="93129-122">Parent Elements</span></span>  
  
|<span data-ttu-id="93129-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="93129-123">Element</span></span>|<span data-ttu-id="93129-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93129-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="93129-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93129-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="93129-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="93129-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93129-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="93129-127">Remarks</span></span>  
 <span data-ttu-id="93129-128">Il comportamento predefinito del Common Language Runtime è eseguire il commit dello stack di thread completo quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="93129-128">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="93129-129">Se un numero elevato di thread deve essere creato in un server con memoria limitata e la maggior parte dei thread utilizzerà pochissimo spazio dello stack, il server potrebbe avere prestazioni migliori se il Common Language Runtime non esegue il commit dello stack di thread completo immediatamente quando viene avviato un thread.</span><span class="sxs-lookup"><span data-stu-id="93129-129">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93129-130">Gli host non gestiti possono usare il flag di avvio `STARTUP_DISABLE_COMMITTHREADSTACK` nell'enumerazione [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="93129-130">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93129-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="93129-131">Example</span></span>  
 <span data-ttu-id="93129-132">L'esempio seguente mostra come disattivare il comportamento predefinito del Common Language Runtime, ovvero eseguire il commit dello stack di thread completo all'avvio del thread.</span><span class="sxs-lookup"><span data-stu-id="93129-132">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="93129-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="93129-133">See also</span></span>

- [<span data-ttu-id="93129-134">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="93129-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="93129-135">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="93129-135">Configuration File Schema</span></span>](../index.md)
