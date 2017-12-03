---
title: '&lt;comContract&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45f4fb83478ef7061a4b14e87d2dce7f9cd9bbf8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="0f688-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="0f688-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="0f688-103">Specifica un contratto del servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="0f688-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="0f688-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0f688-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0f688-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="0f688-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f688-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f688-106">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f688-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0f688-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0f688-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0f688-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f688-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="0f688-109">Attributes</span></span>  
  
|<span data-ttu-id="0f688-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="0f688-110">Attribute</span></span>|<span data-ttu-id="0f688-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f688-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f688-112">contratto</span><span class="sxs-lookup"><span data-stu-id="0f688-112">contract</span></span>|<span data-ttu-id="0f688-113">Stringa che contiene il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="0f688-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="0f688-114">name</span><span class="sxs-lookup"><span data-stu-id="0f688-114">name</span></span>|<span data-ttu-id="0f688-115">Stringa che contiene il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="0f688-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="0f688-116">namespace</span><span class="sxs-lookup"><span data-stu-id="0f688-116">namespace</span></span>|<span data-ttu-id="0f688-117">Stringa che contiene lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="0f688-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="0f688-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="0f688-118">requiresSession</span></span>|<span data-ttu-id="0f688-119">Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="0f688-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="0f688-120">All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="0f688-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="0f688-121">Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="0f688-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="0f688-122">Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0f688-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f688-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0f688-123">Child Elements</span></span>  
  
|<span data-ttu-id="0f688-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f688-124">Element</span></span>|<span data-ttu-id="0f688-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f688-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f688-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="0f688-126">persistableTypes</span></span>|<span data-ttu-id="0f688-127">Tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="0f688-127">All the persistable types.</span></span>|  
|<span data-ttu-id="0f688-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="0f688-128">userDefinedTypes</span></span>|<span data-ttu-id="0f688-129">Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="0f688-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="0f688-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="0f688-130">exposedMethods</span></span>|<span data-ttu-id="0f688-131">Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="0f688-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f688-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0f688-132">Parent Elements</span></span>  
  
|<span data-ttu-id="0f688-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f688-133">Element</span></span>|<span data-ttu-id="0f688-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f688-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f688-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="0f688-135">comContracts</span></span>|<span data-ttu-id="0f688-136">Contiene una raccolta di elementi `comContract`.</span><span class="sxs-lookup"><span data-stu-id="0f688-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f688-137">Note</span><span class="sxs-lookup"><span data-stu-id="0f688-137">Remarks</span></span>  
 <span data-ttu-id="0f688-138">Contratti di servizio COM+ integration sono limitati attualmente allo spazio dei nomi "http://tempuri.org" e nome del contratto è derivato dall'interfaccia COM di supporto.</span><span class="sxs-lookup"><span data-stu-id="0f688-138">COM+ integration service contracts are currently restricted to the "http://tempuri.org" namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="0f688-139">È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0f688-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="0f688-140">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="0f688-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="0f688-141">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="0f688-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f688-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f688-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="0f688-143">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="0f688-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="0f688-144">L'integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="0f688-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="0f688-145">Procedura: configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="0f688-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
