---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: ef980c86efad4fda86cf62148e50688fd22afe49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926097"
---
# <a name="comcontract"></a><span data-ttu-id="71bc6-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="71bc6-101">\<comContract></span></span>
<span data-ttu-id="71bc6-102">Specifica un contratto del servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="71bc6-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="71bc6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="71bc6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="71bc6-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="71bc6-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71bc6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71bc6-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71bc6-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="71bc6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="71bc6-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="71bc6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71bc6-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="71bc6-108">Attributes</span></span>  
  
|<span data-ttu-id="71bc6-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="71bc6-109">Attribute</span></span>|<span data-ttu-id="71bc6-110">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="71bc6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71bc6-111">contract</span><span class="sxs-lookup"><span data-stu-id="71bc6-111">contract</span></span>|<span data-ttu-id="71bc6-112">Stringa che contiene il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="71bc6-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="71bc6-113">name</span><span class="sxs-lookup"><span data-stu-id="71bc6-113">name</span></span>|<span data-ttu-id="71bc6-114">Stringa che contiene il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="71bc6-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="71bc6-115">namespace</span><span class="sxs-lookup"><span data-stu-id="71bc6-115">namespace</span></span>|<span data-ttu-id="71bc6-116">Stringa che contiene lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="71bc6-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="71bc6-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="71bc6-117">requiresSession</span></span>|<span data-ttu-id="71bc6-118">Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="71bc6-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="71bc6-119">All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="71bc6-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="71bc6-120">Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="71bc6-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="71bc6-121">Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="71bc6-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71bc6-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="71bc6-122">Child Elements</span></span>  
  
|<span data-ttu-id="71bc6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="71bc6-123">Element</span></span>|<span data-ttu-id="71bc6-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71bc6-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71bc6-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="71bc6-125">persistableTypes</span></span>|<span data-ttu-id="71bc6-126">Tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="71bc6-126">All the persistable types.</span></span>|  
|<span data-ttu-id="71bc6-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="71bc6-127">userDefinedTypes</span></span>|<span data-ttu-id="71bc6-128">Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="71bc6-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="71bc6-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="71bc6-129">exposedMethods</span></span>|<span data-ttu-id="71bc6-130">Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="71bc6-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71bc6-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="71bc6-131">Parent Elements</span></span>  
  
|<span data-ttu-id="71bc6-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="71bc6-132">Element</span></span>|<span data-ttu-id="71bc6-133">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="71bc6-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71bc6-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="71bc6-134">comContracts</span></span>|<span data-ttu-id="71bc6-135">Contiene una raccolta di elementi `comContract`.</span><span class="sxs-lookup"><span data-stu-id="71bc6-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71bc6-136">Note</span><span class="sxs-lookup"><span data-stu-id="71bc6-136">Remarks</span></span>  
 <span data-ttu-id="71bc6-137">I `http://tempuri.org` contratti di servizio com+ Integration sono attualmente limitati allo spazio dei nomi e il nome del contratto è derivato dall'interfaccia com di supporto.</span><span class="sxs-lookup"><span data-stu-id="71bc6-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="71bc6-138">È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="71bc6-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="71bc6-139">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="71bc6-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="71bc6-140">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="71bc6-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71bc6-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71bc6-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="71bc6-142">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="71bc6-142">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="71bc6-143">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="71bc6-143">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="71bc6-144">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="71bc6-144">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
