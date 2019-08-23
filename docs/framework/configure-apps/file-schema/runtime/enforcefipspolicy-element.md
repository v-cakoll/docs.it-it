---
title: <enforceFIPSPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f13243ddef7020f4d7a50e519ae8281702b0d261
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927424"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="2ce40-102">\<Elemento > enforceFIPSPolicy</span><span class="sxs-lookup"><span data-stu-id="2ce40-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="2ce40-103">Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="2ce40-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="2ce40-104">\<Configuration >-elemento</span><span class="sxs-lookup"><span data-stu-id="2ce40-104">\<configuration> Element</span></span>  
<span data-ttu-id="2ce40-105">\<Elemento runtime ></span><span class="sxs-lookup"><span data-stu-id="2ce40-105">\<runtime> Element</span></span>  
<span data-ttu-id="2ce40-106">\<Elemento > enforceFIPSPolicy</span><span class="sxs-lookup"><span data-stu-id="2ce40-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce40-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ce40-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ce40-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2ce40-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2ce40-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2ce40-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ce40-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="2ce40-110">Attributes</span></span>  
  
|<span data-ttu-id="2ce40-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="2ce40-111">Attribute</span></span>|<span data-ttu-id="2ce40-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ce40-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ce40-113">enabled</span><span class="sxs-lookup"><span data-stu-id="2ce40-113">enabled</span></span>|<span data-ttu-id="2ce40-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2ce40-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="2ce40-115">Specifica se consentire l'applicazione di un requisito di configurazione del computer che gli algoritmi di crittografia devono essere conformi a FIPS.</span><span class="sxs-lookup"><span data-stu-id="2ce40-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2ce40-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="2ce40-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="2ce40-117">Valore</span><span class="sxs-lookup"><span data-stu-id="2ce40-117">Value</span></span>|<span data-ttu-id="2ce40-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2ce40-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="2ce40-119">Se il computer è configurato per richiedere che gli algoritmi di crittografia siano conformi a FIPS, il requisito viene applicato.</span><span class="sxs-lookup"><span data-stu-id="2ce40-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="2ce40-120">Se una classe implementa un algoritmo non conforme a FIPS, i costruttori o `Create` i metodi di tale classe generano eccezioni quando vengono eseguiti nel computer.</span><span class="sxs-lookup"><span data-stu-id="2ce40-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="2ce40-121">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2ce40-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="2ce40-122">Gli algoritmi di crittografia utilizzati dall'applicazione non devono essere conformi a FIPS, indipendentemente dalla configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="2ce40-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ce40-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2ce40-123">Child Elements</span></span>  
 <span data-ttu-id="2ce40-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2ce40-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ce40-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2ce40-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2ce40-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ce40-126">Element</span></span>|<span data-ttu-id="2ce40-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ce40-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2ce40-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2ce40-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2ce40-129">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2ce40-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ce40-130">Note</span><span class="sxs-lookup"><span data-stu-id="2ce40-130">Remarks</span></span>  
 <span data-ttu-id="2ce40-131">A partire da .NET Framework 2,0, la creazione di classi che implementano algoritmi di crittografia è controllata dalla configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="2ce40-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="2ce40-132">Se il computer è configurato per richiedere che gli algoritmi siano conformi a FIPS e una classe implementa un algoritmo non conforme a FIPS, qualsiasi tentativo di creare un'istanza di tale classe genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2ce40-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="2ce40-133">I costruttori generano <xref:System.InvalidOperationException> un'eccezione e `Create` i metodi generano <xref:System.Reflection.TargetInvocationException> un'eccezione con <xref:System.InvalidOperationException> un'eccezione interna.</span><span class="sxs-lookup"><span data-stu-id="2ce40-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="2ce40-134">Se l'applicazione viene eseguita su computer le cui configurazioni richiedono la conformità con FIPS e l'applicazione utilizza un algoritmo non conforme a FIPS, è possibile utilizzare questo elemento nel file di configurazione per impedire che il Common Language Runtime (CLR) da applicazione della conformità FIPS.</span><span class="sxs-lookup"><span data-stu-id="2ce40-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="2ce40-135">Questo elemento è stato introdotto in .NET Framework 2,0 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="2ce40-135">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ce40-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ce40-136">Example</span></span>  
 <span data-ttu-id="2ce40-137">Nell'esempio seguente viene illustrato come impedire a CLR di applicare la conformità FIPS.</span><span class="sxs-lookup"><span data-stu-id="2ce40-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ce40-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ce40-138">See also</span></span>

- [<span data-ttu-id="2ce40-139">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="2ce40-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2ce40-140">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2ce40-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2ce40-141">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="2ce40-141">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
