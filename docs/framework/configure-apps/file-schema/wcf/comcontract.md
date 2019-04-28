---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 8694f83a731363f83cb09de43214eb4b211ef5ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704284"
---
# <a name="comcontract"></a><span data-ttu-id="12b43-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="12b43-101">\<comContract></span></span>
<span data-ttu-id="12b43-102">Specifica un contratto del servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="12b43-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="12b43-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="12b43-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="12b43-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="12b43-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b43-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12b43-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12b43-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="12b43-106">Attributes and Elements</span></span>  
 <span data-ttu-id="12b43-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="12b43-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12b43-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="12b43-108">Attributes</span></span>  
  
|<span data-ttu-id="12b43-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="12b43-109">Attribute</span></span>|<span data-ttu-id="12b43-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12b43-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12b43-111">contratto</span><span class="sxs-lookup"><span data-stu-id="12b43-111">contract</span></span>|<span data-ttu-id="12b43-112">Stringa che contiene il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="12b43-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="12b43-113">name</span><span class="sxs-lookup"><span data-stu-id="12b43-113">name</span></span>|<span data-ttu-id="12b43-114">Stringa che contiene il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="12b43-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="12b43-115">namespace</span><span class="sxs-lookup"><span data-stu-id="12b43-115">namespace</span></span>|<span data-ttu-id="12b43-116">Stringa che contiene lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="12b43-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="12b43-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="12b43-117">requiresSession</span></span>|<span data-ttu-id="12b43-118">Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="12b43-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="12b43-119">All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="12b43-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="12b43-120">Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="12b43-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="12b43-121">Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="12b43-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12b43-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="12b43-122">Child Elements</span></span>  
  
|<span data-ttu-id="12b43-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="12b43-123">Element</span></span>|<span data-ttu-id="12b43-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12b43-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12b43-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="12b43-125">persistableTypes</span></span>|<span data-ttu-id="12b43-126">Tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="12b43-126">All the persistable types.</span></span>|  
|<span data-ttu-id="12b43-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="12b43-127">userDefinedTypes</span></span>|<span data-ttu-id="12b43-128">Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="12b43-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="12b43-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="12b43-129">exposedMethods</span></span>|<span data-ttu-id="12b43-130">Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="12b43-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12b43-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="12b43-131">Parent Elements</span></span>  
  
|<span data-ttu-id="12b43-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="12b43-132">Element</span></span>|<span data-ttu-id="12b43-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12b43-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12b43-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="12b43-134">comContracts</span></span>|<span data-ttu-id="12b43-135">Contiene una raccolta di elementi `comContract`.</span><span class="sxs-lookup"><span data-stu-id="12b43-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12b43-136">Note</span><span class="sxs-lookup"><span data-stu-id="12b43-136">Remarks</span></span>  
 <span data-ttu-id="12b43-137">Contratti di servizio COM+ integration sono limitati attualmente al `http://tempuri.org` spazio dei nomi e nome del contratto è derivato dall'interfaccia COM di supporto.</span><span class="sxs-lookup"><span data-stu-id="12b43-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="12b43-138">È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="12b43-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="12b43-139">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="12b43-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="12b43-140">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="12b43-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b43-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12b43-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="12b43-142">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="12b43-142">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="12b43-143">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="12b43-143">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="12b43-144">Procedura: Configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="12b43-144">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
