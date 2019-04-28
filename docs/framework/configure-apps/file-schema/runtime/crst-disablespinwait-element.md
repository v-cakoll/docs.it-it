---
title: elemento < Crst_DisableSpinWait >
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cde26250db0b3d11c51a18b7ebd378953ae0958
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704830"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="f8dd4-102">\<Crst_DisableSpinWait > elemento</span><span class="sxs-lookup"><span data-stu-id="f8dd4-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="f8dd4-103">Specifica se disabilitare la selezione e in attesa di una sezione critica quando conflitti.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span> \ 
  
 <span data-ttu-id="f8dd4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f8dd4-104">\<configuration></span></span>  
<span data-ttu-id="f8dd4-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="f8dd4-105">\<runtime></span></span>  
<span data-ttu-id="f8dd4-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="f8dd4-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8dd4-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8dd4-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8dd4-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8dd4-108">Attributes and Elements</span></span>

<span data-ttu-id="f8dd4-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8dd4-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8dd4-110">Attributes</span></span>  
  
|<span data-ttu-id="f8dd4-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f8dd4-111">Attribute</span></span>|<span data-ttu-id="f8dd4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8dd4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8dd4-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="f8dd4-113">**enabled**</span></span>|<span data-ttu-id="f8dd4-114">Specifica se è abilitata in attesa di selezione per le sezioni critiche quando essi sono conflitti.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-114">Specifies whether spin-waiting for critical sections is enabled when they are contended.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f8dd4-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="f8dd4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f8dd4-116">Valore</span><span class="sxs-lookup"><span data-stu-id="f8dd4-116">Value</span></span>|<span data-ttu-id="f8dd4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8dd4-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8dd4-118">1</span><span class="sxs-lookup"><span data-stu-id="f8dd4-118">1</span></span>|<span data-ttu-id="f8dd4-119">In attesa di selezione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-119">Spin-waiting is enabled.</span></span>|  
|<span data-ttu-id="f8dd4-120">0</span><span class="sxs-lookup"><span data-stu-id="f8dd4-120">0</span></span>|<span data-ttu-id="f8dd4-121">Rotazione-attesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-121">Spin-waiting is disabled.</span></span> <span data-ttu-id="f8dd4-122">Questo è il valore predefinito</span><span class="sxs-lookup"><span data-stu-id="f8dd4-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8dd4-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8dd4-123">Child Elements</span></span>  
 <span data-ttu-id="f8dd4-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8dd4-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8dd4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f8dd4-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8dd4-126">Element</span></span>|<span data-ttu-id="f8dd4-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8dd4-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f8dd4-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f8dd4-129">Contiene informazioni sulle diverse impostazioni di configurazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f8dd4-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8dd4-130">Example</span></span>  

<span data-ttu-id="f8dd4-131">L'esempio seguente viene disabilitata rotazione-attesa nelle sezioni critiche quando conflitti.</span><span class="sxs-lookup"><span data-stu-id="f8dd4-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8dd4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8dd4-132">See also</span></span>

- [<span data-ttu-id="f8dd4-133">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f8dd4-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="f8dd4-134">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f8dd4-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
