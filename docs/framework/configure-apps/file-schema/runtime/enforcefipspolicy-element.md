---
title: <enforceFIPSPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: 0d6dd291a24928487a040c0427f058dee80bf836
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117379"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="214c8-102">\<elemento > enforceFIPSPolicy</span><span class="sxs-lookup"><span data-stu-id="214c8-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="214c8-103">Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="214c8-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
<span data-ttu-id="214c8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="214c8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="214c8-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="214c8-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="214c8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<enforceFIPSPolicy >**</span><span class="sxs-lookup"><span data-stu-id="214c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="214c8-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="214c8-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="214c8-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="214c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="214c8-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="214c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="214c8-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="214c8-110">Attributes</span></span>  
  
|<span data-ttu-id="214c8-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="214c8-111">Attribute</span></span>|<span data-ttu-id="214c8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="214c8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="214c8-113">enabled</span><span class="sxs-lookup"><span data-stu-id="214c8-113">enabled</span></span>|<span data-ttu-id="214c8-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="214c8-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="214c8-115">Specifica se consentire l'applicazione di un requisito di configurazione del computer che gli algoritmi di crittografia devono essere conformi a FIPS.</span><span class="sxs-lookup"><span data-stu-id="214c8-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="214c8-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="214c8-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="214c8-117">Value</span><span class="sxs-lookup"><span data-stu-id="214c8-117">Value</span></span>|<span data-ttu-id="214c8-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="214c8-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="214c8-119">Se il computer è configurato per richiedere che gli algoritmi di crittografia siano conformi a FIPS, il requisito viene applicato.</span><span class="sxs-lookup"><span data-stu-id="214c8-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="214c8-120">Se una classe implementa un algoritmo non conforme a FIPS, i costruttori o i metodi `Create` per tale classe generano eccezioni quando vengono eseguiti nel computer.</span><span class="sxs-lookup"><span data-stu-id="214c8-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="214c8-121">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="214c8-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="214c8-122">Gli algoritmi di crittografia utilizzati dall'applicazione non devono essere conformi a FIPS, indipendentemente dalla configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="214c8-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="214c8-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="214c8-123">Child Elements</span></span>  
 <span data-ttu-id="214c8-124">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="214c8-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="214c8-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="214c8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="214c8-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="214c8-126">Element</span></span>|<span data-ttu-id="214c8-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="214c8-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="214c8-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="214c8-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="214c8-129">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="214c8-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="214c8-130">Note</span><span class="sxs-lookup"><span data-stu-id="214c8-130">Remarks</span></span>  
 <span data-ttu-id="214c8-131">A partire da .NET Framework 2,0, la creazione di classi che implementano algoritmi di crittografia è controllata dalla configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="214c8-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="214c8-132">Se il computer è configurato per richiedere che gli algoritmi siano conformi a FIPS e una classe implementa un algoritmo non conforme a FIPS, qualsiasi tentativo di creare un'istanza di tale classe genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="214c8-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="214c8-133">I costruttori generano un'eccezione <xref:System.InvalidOperationException> e `Create` metodi generano un'eccezione <xref:System.Reflection.TargetInvocationException> con un'eccezione <xref:System.InvalidOperationException> interna.</span><span class="sxs-lookup"><span data-stu-id="214c8-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="214c8-134">Se l'applicazione viene eseguita su computer le cui configurazioni richiedono la conformità con FIPS e l'applicazione utilizza un algoritmo non conforme a FIPS, è possibile utilizzare questo elemento nel file di configurazione per impedire che il Common Language Runtime (CLR) da applicazione della conformità FIPS.</span><span class="sxs-lookup"><span data-stu-id="214c8-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="214c8-135">Questo elemento è stato introdotto in .NET Framework 2,0 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="214c8-135">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="214c8-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="214c8-136">Example</span></span>  
 <span data-ttu-id="214c8-137">Nell'esempio seguente viene illustrato come impedire a CLR di applicare la conformità FIPS.</span><span class="sxs-lookup"><span data-stu-id="214c8-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="214c8-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="214c8-138">See also</span></span>

- [<span data-ttu-id="214c8-139">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="214c8-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="214c8-140">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="214c8-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="214c8-141">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="214c8-141">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
