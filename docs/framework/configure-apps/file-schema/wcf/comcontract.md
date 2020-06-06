---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850022"
---
# \<comContract>
<span data-ttu-id="ed9f4-101">Specifica un contratto del servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-101">Specifies a COM+ integration service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a><span data-ttu-id="ed9f4-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed9f4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed9f4-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ed9f4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ed9f4-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed9f4-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="ed9f4-105">Attributes</span></span>  
  
|<span data-ttu-id="ed9f4-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="ed9f4-106">Attribute</span></span>|<span data-ttu-id="ed9f4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed9f4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed9f4-108">contract</span><span class="sxs-lookup"><span data-stu-id="ed9f4-108">contract</span></span>|<span data-ttu-id="ed9f4-109">Stringa che contiene il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-109">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="ed9f4-110">name</span><span class="sxs-lookup"><span data-stu-id="ed9f4-110">name</span></span>|<span data-ttu-id="ed9f4-111">Stringa che contiene il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-111">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="ed9f4-112">namespace</span><span class="sxs-lookup"><span data-stu-id="ed9f4-112">namespace</span></span>|<span data-ttu-id="ed9f4-113">Stringa che contiene lo spazio dei nomi del contratto.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-113">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="ed9f4-114">requiresSession</span><span class="sxs-lookup"><span data-stu-id="ed9f4-114">requiresSession</span></span>|<span data-ttu-id="ed9f4-115">Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-115">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="ed9f4-116">All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-116">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="ed9f4-117">Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-117">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="ed9f4-118">Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-118">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed9f4-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ed9f4-119">Child Elements</span></span>  
  
|<span data-ttu-id="ed9f4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed9f4-120">Element</span></span>|<span data-ttu-id="ed9f4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed9f4-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed9f4-122">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="ed9f4-122">persistableTypes</span></span>|<span data-ttu-id="ed9f4-123">Tutti i tipi persistenti.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-123">All the persistable types.</span></span>|  
|<span data-ttu-id="ed9f4-124">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="ed9f4-124">userDefinedTypes</span></span>|<span data-ttu-id="ed9f4-125">Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-125">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="ed9f4-126">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="ed9f4-126">exposedMethods</span></span>|<span data-ttu-id="ed9f4-127">Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-127">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed9f4-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ed9f4-128">Parent Elements</span></span>  
  
|<span data-ttu-id="ed9f4-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed9f4-129">Element</span></span>|<span data-ttu-id="ed9f4-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed9f4-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed9f4-131">comContracts</span><span class="sxs-lookup"><span data-stu-id="ed9f4-131">comContracts</span></span>|<span data-ttu-id="ed9f4-132">Contiene una raccolta di elementi `comContract`.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-132">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed9f4-133">Commenti</span><span class="sxs-lookup"><span data-stu-id="ed9f4-133">Remarks</span></span>  
 <span data-ttu-id="ed9f4-134">I contratti di servizio COM+ Integration sono attualmente limitati allo `http://tempuri.org` spazio dei nomi e il nome del contratto è derivato dall'interfaccia com di supporto.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-134">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="ed9f4-135">È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-135">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="ed9f4-136">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-136">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="ed9f4-137">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="ed9f4-137">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9f4-138">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ed9f4-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="ed9f4-139">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="ed9f4-139">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ed9f4-140">Procedura: configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="ed9f4-140">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
