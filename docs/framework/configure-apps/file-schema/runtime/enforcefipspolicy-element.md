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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117379"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="37806-102">\<enforceFIPSPolicy> Elemento</span><span class="sxs-lookup"><span data-stu-id="37806-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="37806-103">Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).</span><span class="sxs-lookup"><span data-stu-id="37806-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="37806-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37806-104">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37806-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="37806-105">Attributes and Elements</span></span>  
 <span data-ttu-id="37806-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="37806-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37806-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="37806-107">Attributes</span></span>  
  
|<span data-ttu-id="37806-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="37806-108">Attribute</span></span>|<span data-ttu-id="37806-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37806-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37806-110">Enabled</span><span class="sxs-lookup"><span data-stu-id="37806-110">enabled</span></span>|<span data-ttu-id="37806-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="37806-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="37806-112">Specifica se consentire l'applicazione di un requisito di configurazione del computer che gli algoritmi di crittografia devono essere conformi a FIPS.</span><span class="sxs-lookup"><span data-stu-id="37806-112">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="37806-113">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="37806-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="37806-114">Valore</span><span class="sxs-lookup"><span data-stu-id="37806-114">Value</span></span>|<span data-ttu-id="37806-115">Description</span><span class="sxs-lookup"><span data-stu-id="37806-115">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="37806-116">Se il computer è configurato per richiedere che gli algoritmi di crittografia siano conformi a FIPS, il requisito viene applicato.</span><span class="sxs-lookup"><span data-stu-id="37806-116">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="37806-117">Se una classe implementa un algoritmo non conforme a FIPS, i costruttori o i `Create` metodi di tale classe generano eccezioni quando vengono eseguiti nel computer.</span><span class="sxs-lookup"><span data-stu-id="37806-117">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="37806-118">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="37806-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="37806-119">Gli algoritmi di crittografia utilizzati dall'applicazione non devono essere conformi a FIPS, indipendentemente dalla configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="37806-119">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37806-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="37806-120">Child Elements</span></span>  
 <span data-ttu-id="37806-121">No.</span><span class="sxs-lookup"><span data-stu-id="37806-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37806-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="37806-122">Parent Elements</span></span>  
  
|<span data-ttu-id="37806-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="37806-123">Element</span></span>|<span data-ttu-id="37806-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37806-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="37806-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="37806-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="37806-126">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="37806-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37806-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="37806-127">Remarks</span></span>  
 <span data-ttu-id="37806-128">A partire da .NET Framework 2,0, la creazione di classi che implementano algoritmi di crittografia è controllata dalla configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="37806-128">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="37806-129">Se il computer è configurato per richiedere che gli algoritmi siano conformi a FIPS e una classe implementa un algoritmo non conforme a FIPS, qualsiasi tentativo di creare un'istanza di tale classe genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="37806-129">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="37806-130">I costruttori generano un' <xref:System.InvalidOperationException> eccezione e i `Create` metodi generano un'eccezione <xref:System.Reflection.TargetInvocationException> con un' <xref:System.InvalidOperationException> eccezione interna.</span><span class="sxs-lookup"><span data-stu-id="37806-130">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="37806-131">Se l'applicazione viene eseguita su computer le cui configurazioni richiedono la conformità con FIPS e l'applicazione utilizza un algoritmo non conforme a FIPS, è possibile utilizzare questo elemento nel file di configurazione per impedire che il Common Language Runtime (CLR) applichi la conformità FIPS.</span><span class="sxs-lookup"><span data-stu-id="37806-131">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="37806-132">Questo elemento è stato introdotto in .NET Framework 2,0 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="37806-132">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37806-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="37806-133">Example</span></span>  
 <span data-ttu-id="37806-134">Nell'esempio seguente viene illustrato come impedire a CLR di applicare la conformità FIPS.</span><span class="sxs-lookup"><span data-stu-id="37806-134">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="37806-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="37806-135">See also</span></span>

- [<span data-ttu-id="37806-136">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="37806-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="37806-137">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="37806-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="37806-138">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="37806-138">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
