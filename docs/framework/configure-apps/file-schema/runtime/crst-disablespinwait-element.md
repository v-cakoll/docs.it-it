---
title: elemento < Crst_DisableSpinWait >
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f89f0558c11e229fef2ca3cd619e3c033f12c858
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754670"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="a6f5d-102">\<Crst_DisableSpinWait > elemento</span><span class="sxs-lookup"><span data-stu-id="a6f5d-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="a6f5d-103">Specifica se disabilitare la selezione e in attesa di una sezione critica quando conflitti.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="a6f5d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a6f5d-104">\<configuration></span></span>  
<span data-ttu-id="a6f5d-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a6f5d-105">\<runtime></span></span>  
<span data-ttu-id="a6f5d-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="a6f5d-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f5d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6f5d-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6f5d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a6f5d-108">Attributes and Elements</span></span>

<span data-ttu-id="a6f5d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6f5d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="a6f5d-110">Attributes</span></span>  
  
|<span data-ttu-id="a6f5d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="a6f5d-111">Attribute</span></span>|<span data-ttu-id="a6f5d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6f5d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6f5d-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="a6f5d-113">**enabled**</span></span>|<span data-ttu-id="a6f5d-114">Specifica se l'attesa di rotazione per sezioni critiche quando essi sono conflitti è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a6f5d-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="a6f5d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a6f5d-116">Valore</span><span class="sxs-lookup"><span data-stu-id="a6f5d-116">Value</span></span>|<span data-ttu-id="a6f5d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6f5d-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6f5d-118">1</span><span class="sxs-lookup"><span data-stu-id="a6f5d-118">1</span></span>|<span data-ttu-id="a6f5d-119">Disabilitare la rotazione-attesa quando non è possibile acquisire una sezione critica.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="a6f5d-120">0</span><span class="sxs-lookup"><span data-stu-id="a6f5d-120">0</span></span>|<span data-ttu-id="a6f5d-121">Non disabilitare la rotazione-attesa quando non è possibile acquisire una sezione critica.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="a6f5d-122">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6f5d-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a6f5d-123">Child Elements</span></span>  
 <span data-ttu-id="a6f5d-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6f5d-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a6f5d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a6f5d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6f5d-126">Element</span></span>|<span data-ttu-id="a6f5d-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6f5d-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a6f5d-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a6f5d-129">Contiene informazioni sulle diverse impostazioni di configurazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a6f5d-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6f5d-130">Example</span></span>  

<span data-ttu-id="a6f5d-131">L'esempio seguente viene disabilitata rotazione-attesa nelle sezioni critiche quando conflitti.</span><span class="sxs-lookup"><span data-stu-id="a6f5d-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6f5d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6f5d-132">See also</span></span>

- [<span data-ttu-id="a6f5d-133">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="a6f5d-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a6f5d-134">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a6f5d-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
