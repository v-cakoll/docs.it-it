---
title: < elemento > Crst_DisableSpinWait
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a91e21120ecebbe7af2fb93798bc68d274fa92c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252719"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="01c95-102">\<Elemento > Crst_DisableSpinWait</span><span class="sxs-lookup"><span data-stu-id="01c95-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="01c95-103">Specifica se disabilitare lo spin-waiting per una sezione critica in caso di conflitto.</span><span class="sxs-lookup"><span data-stu-id="01c95-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
<span data-ttu-id="01c95-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="01c95-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="01c95-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="01c95-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="01c95-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> Crst_DisableSpinWait**</span><span class="sxs-lookup"><span data-stu-id="01c95-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c95-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01c95-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01c95-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="01c95-108">Attributes and Elements</span></span>

<span data-ttu-id="01c95-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="01c95-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01c95-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="01c95-110">Attributes</span></span>  
  
|<span data-ttu-id="01c95-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="01c95-111">Attribute</span></span>|<span data-ttu-id="01c95-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01c95-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01c95-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="01c95-113">**enabled**</span></span>|<span data-ttu-id="01c95-114">Specifica se la rotazione in attesa di sezioni critiche quando sono in conflitto è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="01c95-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="01c95-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="01c95-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="01c95-116">Valore</span><span class="sxs-lookup"><span data-stu-id="01c95-116">Value</span></span>|<span data-ttu-id="01c95-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="01c95-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="01c95-118">1</span><span class="sxs-lookup"><span data-stu-id="01c95-118">1</span></span>|<span data-ttu-id="01c95-119">Disabilitare la rotazione in attesa quando non è possibile acquisire una sezione critica.</span><span class="sxs-lookup"><span data-stu-id="01c95-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="01c95-120">0</span><span class="sxs-lookup"><span data-stu-id="01c95-120">0</span></span>|<span data-ttu-id="01c95-121">Non disabilitare la rotazione in attesa quando non è possibile acquisire una sezione critica.</span><span class="sxs-lookup"><span data-stu-id="01c95-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="01c95-122">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="01c95-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01c95-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="01c95-123">Child Elements</span></span>  
 <span data-ttu-id="01c95-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="01c95-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01c95-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="01c95-125">Parent Elements</span></span>  
  
|<span data-ttu-id="01c95-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="01c95-126">Element</span></span>|<span data-ttu-id="01c95-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01c95-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="01c95-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01c95-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="01c95-129">Contiene informazioni sulle varie impostazioni di configurazione del runtime.</span><span class="sxs-lookup"><span data-stu-id="01c95-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="01c95-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="01c95-130">Example</span></span>  

<span data-ttu-id="01c95-131">Nell'esempio seguente viene disabilitata la rotazione in attesa nelle sezioni critiche quando è in conflitto.</span><span class="sxs-lookup"><span data-stu-id="01c95-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01c95-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01c95-132">See also</span></span>

- [<span data-ttu-id="01c95-133">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="01c95-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="01c95-134">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="01c95-134">Configuration File Schema</span></span>](../index.md)
