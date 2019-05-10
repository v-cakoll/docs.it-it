---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 5d6bfb1e4aa1651cd8c3a869f681d71cfb15725c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751880"
---
# <a name="comcontract"></a><span data-ttu-id="49053-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="49053-101">\<comContract></span></span>
<span data-ttu-id="49053-102">Specifica un contratto del servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="49053-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="49053-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="49053-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="49053-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="49053-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49053-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49053-105">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49053-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="49053-106">Attributes and Elements</span></span>  
 <span data-ttu-id="49053-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="49053-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49053-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="49053-108">Attributes</span></span>  
  
|<span data-ttu-id="49053-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="49053-109">Attribute</span></span>|<span data-ttu-id="49053-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49053-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49053-111">contratto</span><span class="sxs-lookup"><span data-stu-id="49053-111">contract</span></span>|<span data-ttu-id="49053-112">Stringa che contiene il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="49053-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="49053-113">name</span><span class="sxs-lookup"><span data-stu-id="49053-113">name</span></span>|<span data-ttu-id="49053-114">Stringa che contiene il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="49053-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="49053-115">namespace</span><span class="sxs-lookup"><span data-stu-id="49053-115">namespace</span></span>|<span data-ttu-id="49053-116">Stringa che contiene lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="49053-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="49053-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="49053-117">requiresSession</span></span>|<span data-ttu-id="49053-118">Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="49053-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="49053-119">All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="49053-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="49053-120">Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="49053-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="49053-121">Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="49053-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49053-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="49053-122">Child Elements</span></span>  
  
|<span data-ttu-id="49053-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="49053-123">Element</span></span>|<span data-ttu-id="49053-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49053-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49053-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="49053-125">persistableTypes</span></span>|<span data-ttu-id="49053-126">Tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="49053-126">All the persistable types.</span></span>|  
|<span data-ttu-id="49053-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="49053-127">userDefinedTypes</span></span>|<span data-ttu-id="49053-128">Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="49053-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="49053-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="49053-129">exposedMethods</span></span>|<span data-ttu-id="49053-130">Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="49053-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49053-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="49053-131">Parent Elements</span></span>  
  
|<span data-ttu-id="49053-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="49053-132">Element</span></span>|<span data-ttu-id="49053-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49053-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49053-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="49053-134">comContracts</span></span>|<span data-ttu-id="49053-135">Contiene una raccolta di elementi `comContract`.</span><span class="sxs-lookup"><span data-stu-id="49053-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49053-136">Note</span><span class="sxs-lookup"><span data-stu-id="49053-136">Remarks</span></span>  
 <span data-ttu-id="49053-137">Contratti di servizio COM+ integration sono limitati attualmente al `http://tempuri.org` spazio dei nomi e nome del contratto è derivato dall'interfaccia COM di supporto.</span><span class="sxs-lookup"><span data-stu-id="49053-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="49053-138">È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="49053-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="49053-139">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="49053-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
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
  
 <span data-ttu-id="49053-140">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="49053-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49053-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49053-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="49053-142">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="49053-142">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="49053-143">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="49053-143">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="49053-144">Procedura: Configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="49053-144">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
