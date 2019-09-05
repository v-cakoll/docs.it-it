---
title: <shadowCopyVerifyByTimestamp> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79d44ff255b1fc12efc6e8488eeab231b9276b90
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252312"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="6986c-102">Elemento \<shadowCopyVerifyByTimestamp></span><span class="sxs-lookup"><span data-stu-id="6986c-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="6986c-103">Specifica se la copia shadow usa il comportamento di avvio predefinito introdotto nel .NET Framework 4 o Ripristina il comportamento di avvio delle versioni precedenti del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6986c-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
<span data-ttu-id="6986c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6986c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6986c-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="6986c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="6986c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> shadowCopyVerifyByTimestamp**</span><span class="sxs-lookup"><span data-stu-id="6986c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6986c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6986c-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6986c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6986c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6986c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6986c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6986c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6986c-110">Attributes</span></span>  
  
|<span data-ttu-id="6986c-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="6986c-111">Attribute</span></span>|<span data-ttu-id="6986c-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6986c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6986c-113">enabled</span><span class="sxs-lookup"><span data-stu-id="6986c-113">enabled</span></span>|<span data-ttu-id="6986c-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6986c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="6986c-115">Specifica se i domini applicazione che usano la copia shadow confrontano i timestamp dell'assembly al momento dell'avvio, per determinare se un assembly è stato aggiornato prima della copia shadow dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="6986c-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6986c-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="6986c-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="6986c-117">Valore</span><span class="sxs-lookup"><span data-stu-id="6986c-117">Value</span></span>|<span data-ttu-id="6986c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6986c-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6986c-119">true</span><span class="sxs-lookup"><span data-stu-id="6986c-119">true</span></span>|<span data-ttu-id="6986c-120">All'avvio, copia solo gli assembly che sono stati aggiornati dopo l'ultima copia nella directory della copia shadow.</span><span class="sxs-lookup"><span data-stu-id="6986c-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="6986c-121">Si tratta dell'impostazione predefinita per il .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6986c-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="6986c-122">false</span><span class="sxs-lookup"><span data-stu-id="6986c-122">false</span></span>|<span data-ttu-id="6986c-123">Ripristina il comportamento di avvio delle versioni precedenti del .NET Framework, ovvero la copia di tutti i file all'avvio.</span><span class="sxs-lookup"><span data-stu-id="6986c-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6986c-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6986c-124">Child Elements</span></span>  
 <span data-ttu-id="6986c-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6986c-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6986c-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6986c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="6986c-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="6986c-127">Element</span></span>|<span data-ttu-id="6986c-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6986c-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6986c-129">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6986c-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6986c-130">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6986c-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6986c-131">Note</span><span class="sxs-lookup"><span data-stu-id="6986c-131">Remarks</span></span>  
 <span data-ttu-id="6986c-132">A partire da .NET Framework 4, gli assembly vengono replicati solo se i timestamp indicano che sono stati modificati dopo l'ultima copia nella directory della copia shadow.</span><span class="sxs-lookup"><span data-stu-id="6986c-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="6986c-133">Ciò migliora i tempi di avvio per molte applicazioni che usano la copia shadow, come descritto in assembly per la [Copia Shadow](../../../app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="6986c-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="6986c-134">Le applicazioni con una percentuale e una frequenza elevate di aggiornamenti dell'assembly non possono trarre vantaggio da questa modifica nel comportamento.</span><span class="sxs-lookup"><span data-stu-id="6986c-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="6986c-135">In tal caso, è possibile utilizzare questo elemento per ripristinare il comportamento delle versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6986c-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6986c-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="6986c-136">Example</span></span>  
 <span data-ttu-id="6986c-137">Nell'esempio seguente viene illustrato come disabilitare il comportamento di avvio predefinito della copia shadow nella .NET Framework 4 e ripristinare il comportamento di avvio delle versioni precedenti del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6986c-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6986c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6986c-138">See also</span></span>

- [<span data-ttu-id="6986c-139">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="6986c-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6986c-140">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6986c-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6986c-141">Creazione di copie replicate di assembly</span><span class="sxs-lookup"><span data-stu-id="6986c-141">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
