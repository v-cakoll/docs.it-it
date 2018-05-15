---
title: '&lt;userDefinedType&gt;'
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: ffa9480312c278097ae110c686fb507209c117e1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltuserdefinedtypegt"></a><span data-ttu-id="2ae61-102">&lt;userDefinedType&gt;</span><span class="sxs-lookup"><span data-stu-id="2ae61-102">&lt;userDefinedType&gt;</span></span>
<span data-ttu-id="2ae61-103">Rappresenta un tipo definito dall'utente (UDT) che deve essere incluso nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="2ae61-103">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
 <span data-ttu-id="2ae61-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2ae61-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2ae61-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="2ae61-105">\<comContracts></span></span>  
<span data-ttu-id="2ae61-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="2ae61-106">\<comContract></span></span>  
<span data-ttu-id="2ae61-107">\<userDefinedTypes ></span><span class="sxs-lookup"><span data-stu-id="2ae61-107">\<userDefinedTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae61-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ae61-108">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ae61-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2ae61-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ae61-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2ae61-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ae61-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="2ae61-111">Attributes</span></span>  
  
|<span data-ttu-id="2ae61-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="2ae61-112">Attribute</span></span>|<span data-ttu-id="2ae61-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ae61-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="2ae61-114">Attributo facoltativo contenente una stringa che fornisce il nome tipo leggibile.</span><span class="sxs-lookup"><span data-stu-id="2ae61-114">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="2ae61-115">Non viene usato dal runtime, ma aiuta un reader a distinguere i tipi.</span><span class="sxs-lookup"><span data-stu-id="2ae61-115">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="2ae61-116">Stringa GUID che identifica il tipo specifico definito dall'utente all'interno della libreria dei tipi registrati.</span><span class="sxs-lookup"><span data-stu-id="2ae61-116">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="2ae61-117">Stringa GUID che identifica la libreria dei tipi registrata che definisce il tipo.</span><span class="sxs-lookup"><span data-stu-id="2ae61-117">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="2ae61-118">Stringa che identifica la versione della libreria dei tipi che definisce il tipo.</span><span class="sxs-lookup"><span data-stu-id="2ae61-118">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ae61-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2ae61-119">Child Elements</span></span>  
 <span data-ttu-id="2ae61-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2ae61-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ae61-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2ae61-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2ae61-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ae61-122">Element</span></span>|<span data-ttu-id="2ae61-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ae61-123">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="2ae61-124">Raccolta di elementi `userDefinedType`.</span><span class="sxs-lookup"><span data-stu-id="2ae61-124">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ae61-125">Note</span><span class="sxs-lookup"><span data-stu-id="2ae61-125">Remarks</span></span>  
 <span data-ttu-id="2ae61-126">Il runtime di integrazione COM+ crea servizi controllando la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="2ae61-126">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="2ae61-127">Quando un componente COM+ contiene metodi che passano una VARIANT, il sistema non può determinare i tipi effettivi da passare prima della fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2ae61-127">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="2ae61-128">Quando si tenta pertanto di passare un tipo definito dall'utente (UDT) all'interno di una VARIANT, l'operazione non riesce perché non è un tipo noto per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="2ae61-128">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="2ae61-129">Per aggirare questo problema, è possibile aggiungere tipi definiti dall'utente al file di configurazione in modo che possano essere inclusi come tipi noti nel contratto di servizio appropriato.</span><span class="sxs-lookup"><span data-stu-id="2ae61-129">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="2ae61-130">A tale scopo, è necessario identificare in modo univoco i tipi definiti dall'utente e i contratti, ovvero le interfacce COM originali che li usano.</span><span class="sxs-lookup"><span data-stu-id="2ae61-130">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="2ae61-131">L'esempio seguente illustra come aggiungere alla sezione <`userDefinedTypes`> del file di configurazione due tipi specifici definiti dall'utente per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="2ae61-131">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <userDefinedTypes>  
         <userDefinedType name="CustomerType"  
            typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"  
            typeLibVersion="1.0"  
            typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">  
         </userDefinedType>  
         <userDefinedType name="AddressType"  
            typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"  
            typeLibVersion="1.0"  
            typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">  
         </userDefinedType>  
      </userDefinedTypes>  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="2ae61-132">Quando il servizio viene inizializzato, il runtime di integrazione ricerca i tipi specificati e li aggiunge alla raccolta dei tipi noti per i contratti specificati.</span><span class="sxs-lookup"><span data-stu-id="2ae61-132">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae61-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ae61-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>  
 <xref:System.ServiceModel.Configuration.ComUdtElementCollection>  
 <xref:System.ServiceModel.Configuration.ComUdtElement>  
 [<span data-ttu-id="2ae61-134">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="2ae61-134">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="2ae61-135">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="2ae61-135">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="2ae61-136">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="2ae61-136">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
