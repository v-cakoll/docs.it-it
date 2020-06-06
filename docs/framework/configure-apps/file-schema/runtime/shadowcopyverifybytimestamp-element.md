---
title: <shadowCopyVerifyByTimestamp> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 160f14c856735e1ceac8635506aea52454faea43
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115733"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="a17ca-102">\<shadowCopyVerifyByTimestamp> Elemento</span><span class="sxs-lookup"><span data-stu-id="a17ca-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="a17ca-103">Specifica se la copia shadow usa il comportamento di avvio predefinito introdotto nel .NET Framework 4 o Ripristina il comportamento di avvio delle versioni precedenti del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a17ca-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**  
  
## <a name="syntax"></a><span data-ttu-id="a17ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a17ca-104">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a17ca-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a17ca-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a17ca-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a17ca-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a17ca-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a17ca-107">Attributes</span></span>  
  
|<span data-ttu-id="a17ca-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="a17ca-108">Attribute</span></span>|<span data-ttu-id="a17ca-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a17ca-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a17ca-110">Enabled</span><span class="sxs-lookup"><span data-stu-id="a17ca-110">enabled</span></span>|<span data-ttu-id="a17ca-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a17ca-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="a17ca-112">Specifica se i domini applicazione che usano la copia shadow confrontano i timestamp dell'assembly al momento dell'avvio, per determinare se un assembly è stato aggiornato prima della copia shadow dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a17ca-112">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a17ca-113">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="a17ca-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="a17ca-114">Valore</span><span class="sxs-lookup"><span data-stu-id="a17ca-114">Value</span></span>|<span data-ttu-id="a17ca-115">Description</span><span class="sxs-lookup"><span data-stu-id="a17ca-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a17ca-116">true</span><span class="sxs-lookup"><span data-stu-id="a17ca-116">true</span></span>|<span data-ttu-id="a17ca-117">All'avvio, copia solo gli assembly che sono stati aggiornati dopo l'ultima copia nella directory della copia shadow.</span><span class="sxs-lookup"><span data-stu-id="a17ca-117">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="a17ca-118">Si tratta dell'impostazione predefinita per il .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a17ca-118">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="a17ca-119">false</span><span class="sxs-lookup"><span data-stu-id="a17ca-119">false</span></span>|<span data-ttu-id="a17ca-120">Ripristina il comportamento di avvio delle versioni precedenti del .NET Framework, ovvero la copia di tutti i file all'avvio.</span><span class="sxs-lookup"><span data-stu-id="a17ca-120">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a17ca-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a17ca-121">Child Elements</span></span>  
 <span data-ttu-id="a17ca-122">No.</span><span class="sxs-lookup"><span data-stu-id="a17ca-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a17ca-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a17ca-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a17ca-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a17ca-124">Element</span></span>|<span data-ttu-id="a17ca-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a17ca-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a17ca-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a17ca-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a17ca-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a17ca-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a17ca-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="a17ca-128">Remarks</span></span>  
 <span data-ttu-id="a17ca-129">A partire da .NET Framework 4, gli assembly vengono replicati solo se i timestamp indicano che sono stati modificati dopo l'ultima copia nella directory della copia shadow.</span><span class="sxs-lookup"><span data-stu-id="a17ca-129">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="a17ca-130">Ciò migliora i tempi di avvio per molte applicazioni che usano la copia shadow, come descritto in assembly per la [Copia Shadow](../../../app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="a17ca-130">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="a17ca-131">Le applicazioni con una percentuale e una frequenza elevate di aggiornamenti dell'assembly non possono trarre vantaggio da questa modifica nel comportamento.</span><span class="sxs-lookup"><span data-stu-id="a17ca-131">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="a17ca-132">In tal caso, è possibile utilizzare questo elemento per ripristinare il comportamento delle versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a17ca-132">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a17ca-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="a17ca-133">Example</span></span>  
 <span data-ttu-id="a17ca-134">Nell'esempio seguente viene illustrato come disabilitare il comportamento di avvio predefinito della copia shadow nella .NET Framework 4 e ripristinare il comportamento di avvio delle versioni precedenti del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a17ca-134">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a17ca-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a17ca-135">See also</span></span>

- [<span data-ttu-id="a17ca-136">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="a17ca-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a17ca-137">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a17ca-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a17ca-138">Creazione di copie replicate di assembly</span><span class="sxs-lookup"><span data-stu-id="a17ca-138">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
