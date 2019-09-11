---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850022"
---
# <a name="comcontract"></a><span data-ttu-id="aefaf-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="aefaf-101">\<comContract></span></span>
<span data-ttu-id="aefaf-102">Specifica un contratto del servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="aefaf-102">Specifies a COM+ integration service contract.</span></span>  
  
<span data-ttu-id="aefaf-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aefaf-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aefaf-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aefaf-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aefaf-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comcontratti >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="aefaf-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="aefaf-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> comContract**</span><span class="sxs-lookup"><span data-stu-id="aefaf-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aefaf-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aefaf-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aefaf-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aefaf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aefaf-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aefaf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aefaf-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="aefaf-110">Attributes</span></span>  
  
|<span data-ttu-id="aefaf-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="aefaf-111">Attribute</span></span>|<span data-ttu-id="aefaf-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="aefaf-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aefaf-113">contract</span><span class="sxs-lookup"><span data-stu-id="aefaf-113">contract</span></span>|<span data-ttu-id="aefaf-114">Stringa che contiene il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="aefaf-114">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="aefaf-115">name</span><span class="sxs-lookup"><span data-stu-id="aefaf-115">name</span></span>|<span data-ttu-id="aefaf-116">Stringa che contiene il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="aefaf-116">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="aefaf-117">namespace</span><span class="sxs-lookup"><span data-stu-id="aefaf-117">namespace</span></span>|<span data-ttu-id="aefaf-118">Stringa che contiene lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="aefaf-118">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="aefaf-119">requiresSession</span><span class="sxs-lookup"><span data-stu-id="aefaf-119">requiresSession</span></span>|<span data-ttu-id="aefaf-120">Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="aefaf-120">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="aefaf-121">All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="aefaf-121">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="aefaf-122">Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="aefaf-122">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="aefaf-123">Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="aefaf-123">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aefaf-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aefaf-124">Child Elements</span></span>  
  
|<span data-ttu-id="aefaf-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="aefaf-125">Element</span></span>|<span data-ttu-id="aefaf-126">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="aefaf-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aefaf-127">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="aefaf-127">persistableTypes</span></span>|<span data-ttu-id="aefaf-128">Tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="aefaf-128">All the persistable types.</span></span>|  
|<span data-ttu-id="aefaf-129">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="aefaf-129">userDefinedTypes</span></span>|<span data-ttu-id="aefaf-130">Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="aefaf-130">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="aefaf-131">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="aefaf-131">exposedMethods</span></span>|<span data-ttu-id="aefaf-132">Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="aefaf-132">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aefaf-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aefaf-133">Parent Elements</span></span>  
  
|<span data-ttu-id="aefaf-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="aefaf-134">Element</span></span>|<span data-ttu-id="aefaf-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aefaf-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aefaf-136">comContracts</span><span class="sxs-lookup"><span data-stu-id="aefaf-136">comContracts</span></span>|<span data-ttu-id="aefaf-137">Contiene una raccolta di elementi `comContract`.</span><span class="sxs-lookup"><span data-stu-id="aefaf-137">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aefaf-138">Note</span><span class="sxs-lookup"><span data-stu-id="aefaf-138">Remarks</span></span>  
 <span data-ttu-id="aefaf-139">I `http://tempuri.org` contratti di servizio com+ Integration sono attualmente limitati allo spazio dei nomi e il nome del contratto è derivato dall'interfaccia com di supporto.</span><span class="sxs-lookup"><span data-stu-id="aefaf-139">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="aefaf-140">È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="aefaf-140">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="aefaf-141">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="aefaf-141">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="aefaf-142">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="aefaf-142">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefaf-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aefaf-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="aefaf-144">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="aefaf-144">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="aefaf-145">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="aefaf-145">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="aefaf-146">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="aefaf-146">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
