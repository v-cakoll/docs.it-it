---
title: '&lt;comContract&gt;'
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: e2addbada7f55076ae919d93c897991a7ec0fcd8
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2018
ms.locfileid: "46490452"
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="cd26f-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="cd26f-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="cd26f-103">Specifica un contratto del servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="cd26f-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="cd26f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cd26f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cd26f-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="cd26f-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd26f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd26f-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd26f-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cd26f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cd26f-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cd26f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd26f-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="cd26f-109">Attributes</span></span>  
  
|<span data-ttu-id="cd26f-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="cd26f-110">Attribute</span></span>|<span data-ttu-id="cd26f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd26f-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd26f-112">contratto</span><span class="sxs-lookup"><span data-stu-id="cd26f-112">contract</span></span>|<span data-ttu-id="cd26f-113">Stringa che contiene il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="cd26f-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="cd26f-114">name</span><span class="sxs-lookup"><span data-stu-id="cd26f-114">name</span></span>|<span data-ttu-id="cd26f-115">Stringa che contiene il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="cd26f-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="cd26f-116">namespace</span><span class="sxs-lookup"><span data-stu-id="cd26f-116">namespace</span></span>|<span data-ttu-id="cd26f-117">Stringa che contiene lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="cd26f-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="cd26f-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="cd26f-118">requiresSession</span></span>|<span data-ttu-id="cd26f-119">Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="cd26f-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="cd26f-120">All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="cd26f-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="cd26f-121">Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="cd26f-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="cd26f-122">Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd26f-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd26f-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cd26f-123">Child Elements</span></span>  
  
|<span data-ttu-id="cd26f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd26f-124">Element</span></span>|<span data-ttu-id="cd26f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd26f-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd26f-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="cd26f-126">persistableTypes</span></span>|<span data-ttu-id="cd26f-127">Tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="cd26f-127">All the persistable types.</span></span>|  
|<span data-ttu-id="cd26f-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="cd26f-128">userDefinedTypes</span></span>|<span data-ttu-id="cd26f-129">Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="cd26f-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="cd26f-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="cd26f-130">exposedMethods</span></span>|<span data-ttu-id="cd26f-131">Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="cd26f-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd26f-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cd26f-132">Parent Elements</span></span>  
  
|<span data-ttu-id="cd26f-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd26f-133">Element</span></span>|<span data-ttu-id="cd26f-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd26f-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd26f-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="cd26f-135">comContracts</span></span>|<span data-ttu-id="cd26f-136">Contiene una raccolta di elementi `comContract`.</span><span class="sxs-lookup"><span data-stu-id="cd26f-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd26f-137">Note</span><span class="sxs-lookup"><span data-stu-id="cd26f-137">Remarks</span></span>  
 <span data-ttu-id="cd26f-138">Contratti di servizio COM+ integration sono limitati attualmente al `http://tempuri.org` spazio dei nomi e nome del contratto è derivato dall'interfaccia COM di supporto.</span><span class="sxs-lookup"><span data-stu-id="cd26f-138">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="cd26f-139">È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cd26f-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="cd26f-140">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="cd26f-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="cd26f-141">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="cd26f-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd26f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd26f-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="cd26f-143">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="cd26f-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="cd26f-144">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="cd26f-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="cd26f-145">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="cd26f-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
