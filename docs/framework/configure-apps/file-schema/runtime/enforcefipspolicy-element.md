---
title: '&lt;enforceFIPSPolicy&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9040bf2548964cf6df5f4fd87ee9f6d979c7df1e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746215"
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="7e495-102">&lt;enforceFIPSPolicy&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="7e495-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="7e495-103">Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="7e495-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="7e495-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="7e495-104">\<configuration> Element</span></span>  
<span data-ttu-id="7e495-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="7e495-105">\<runtime> Element</span></span>  
<span data-ttu-id="7e495-106">\<enforceFIPSPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="7e495-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e495-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e495-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e495-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7e495-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7e495-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7e495-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e495-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="7e495-110">Attributes</span></span>  
  
|<span data-ttu-id="7e495-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="7e495-111">Attribute</span></span>|<span data-ttu-id="7e495-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e495-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e495-113">enabled</span><span class="sxs-lookup"><span data-stu-id="7e495-113">enabled</span></span>|<span data-ttu-id="7e495-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7e495-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="7e495-115">Specifica se abilitare l'applicazione di un requisito di configurazione di computer che gli algoritmi di crittografia devono essere conformi a FIPS.</span><span class="sxs-lookup"><span data-stu-id="7e495-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7e495-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="7e495-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="7e495-117">Valore</span><span class="sxs-lookup"><span data-stu-id="7e495-117">Value</span></span>|<span data-ttu-id="7e495-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e495-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="7e495-119">Se il computer è configurato per richiedere gli algoritmi di crittografia per essere conforme a FIPS, tale requisito viene applicato.</span><span class="sxs-lookup"><span data-stu-id="7e495-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="7e495-120">Se una classe che implementa un algoritmo che non è conforme a FIPS, i costruttori o `Create` metodi per tale classe generano eccezioni quando vengono eseguiti nel computer.</span><span class="sxs-lookup"><span data-stu-id="7e495-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="7e495-121">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7e495-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="7e495-122">Gli algoritmi di crittografia utilizzati dall'applicazione non sono necessari affinché sia conforme a FIPS, indipendentemente dalla configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="7e495-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e495-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7e495-123">Child Elements</span></span>  
 <span data-ttu-id="7e495-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7e495-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e495-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7e495-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7e495-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e495-126">Element</span></span>|<span data-ttu-id="7e495-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e495-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7e495-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e495-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7e495-129">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7e495-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e495-130">Note</span><span class="sxs-lookup"><span data-stu-id="7e495-130">Remarks</span></span>  
 <span data-ttu-id="7e495-131">A partire da .NET Framework 2.0, la creazione di classi che implementano gli algoritmi di crittografia è controllata dalla configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="7e495-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="7e495-132">Se il computer è configurato per richiedere agli algoritmi di essere conforme a FIPS e una classe che implementa un algoritmo che non è conforme a FIPS, qualsiasi tentativo di creare un'istanza di tale classe genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7e495-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="7e495-133">Costruttori di generano un <xref:System.InvalidOperationException> eccezione, e `Create` metodi generano un <xref:System.Reflection.TargetInvocationException> eccezione con un inner <xref:System.InvalidOperationException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="7e495-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="7e495-134">Se l'applicazione viene eseguita nei computer con configurazioni richiedono la conformità con FIPS e l'applicazione utilizza un algoritmo che non è conforme a FIPS, è possibile utilizzare questo elemento nel file di configurazione per evitare di common language runtime (CLR) di applicazione della conformità FIPS.</span><span class="sxs-lookup"><span data-stu-id="7e495-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="7e495-135">Questo elemento è stato introdotto nel [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e495-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e495-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e495-136">Example</span></span>  
 <span data-ttu-id="7e495-137">Nell'esempio seguente viene illustrato come impedire l'applicazione della conformità FIPS CLR.</span><span class="sxs-lookup"><span data-stu-id="7e495-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e495-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e495-138">See Also</span></span>  
 [<span data-ttu-id="7e495-139">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7e495-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="7e495-140">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7e495-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="7e495-141">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="7e495-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
