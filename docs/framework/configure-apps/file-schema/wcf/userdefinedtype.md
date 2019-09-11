---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 7a76e5a90fe3218bc0302501b71daa9de0b098bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854842"
---
# <a name="userdefinedtype"></a><span data-ttu-id="8b66e-101">\<> di</span><span class="sxs-lookup"><span data-stu-id="8b66e-101">\<userDefinedType></span></span>
<span data-ttu-id="8b66e-102">Rappresenta un tipo definito dall'utente (UDT) che deve essere incluso nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="8b66e-102">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
<span data-ttu-id="8b66e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8b66e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8b66e-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8b66e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8b66e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comcontratti >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="8b66e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="8b66e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> comContract**](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="8b66e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="8b66e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> userDefinedTypes**](userdefinedtypes.md)</span><span class="sxs-lookup"><span data-stu-id="8b66e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)</span></span>\
<span data-ttu-id="8b66e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di**</span><span class="sxs-lookup"><span data-stu-id="8b66e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b66e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b66e-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b66e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8b66e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8b66e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8b66e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b66e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8b66e-112">Attributes</span></span>  
  
|<span data-ttu-id="8b66e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="8b66e-113">Attribute</span></span>|<span data-ttu-id="8b66e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b66e-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="8b66e-115">Attributo facoltativo contenente una stringa che fornisce il nome tipo leggibile.</span><span class="sxs-lookup"><span data-stu-id="8b66e-115">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="8b66e-116">Non viene usato dal runtime, ma aiuta un reader a distinguere i tipi.</span><span class="sxs-lookup"><span data-stu-id="8b66e-116">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="8b66e-117">Stringa GUID che identifica il tipo specifico definito dall'utente all'interno della libreria dei tipi registrati.</span><span class="sxs-lookup"><span data-stu-id="8b66e-117">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="8b66e-118">Stringa GUID che identifica la libreria dei tipi registrata che definisce il tipo.</span><span class="sxs-lookup"><span data-stu-id="8b66e-118">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="8b66e-119">Stringa che identifica la versione della libreria dei tipi che definisce il tipo.</span><span class="sxs-lookup"><span data-stu-id="8b66e-119">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b66e-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8b66e-120">Child Elements</span></span>  
 <span data-ttu-id="8b66e-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8b66e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b66e-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8b66e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8b66e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b66e-123">Element</span></span>|<span data-ttu-id="8b66e-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b66e-124">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="8b66e-125">Raccolta di elementi `userDefinedType`.</span><span class="sxs-lookup"><span data-stu-id="8b66e-125">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b66e-126">Note</span><span class="sxs-lookup"><span data-stu-id="8b66e-126">Remarks</span></span>  
 <span data-ttu-id="8b66e-127">Il runtime di integrazione COM+ crea servizi controllando la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="8b66e-127">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="8b66e-128">Quando un componente COM+ contiene metodi che passano una VARIANT, il sistema non può determinare i tipi effettivi da passare prima della fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8b66e-128">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="8b66e-129">Quando si tenta pertanto di passare un tipo definito dall'utente (UDT) all'interno di una VARIANT, l'operazione non riesce perché non è un tipo noto per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="8b66e-129">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="8b66e-130">Per aggirare questo problema, è possibile aggiungere tipi definiti dall'utente al file di configurazione in modo che possano essere inclusi come tipi noti nel contratto di servizio appropriato.</span><span class="sxs-lookup"><span data-stu-id="8b66e-130">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="8b66e-131">A tale scopo, è necessario identificare in modo univoco i tipi definiti dall'utente e i contratti, ovvero le interfacce COM originali che li usano.</span><span class="sxs-lookup"><span data-stu-id="8b66e-131">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="8b66e-132">Nell'esempio seguente viene illustrata l'aggiunta di due tipi`userDefinedTypes`specifici definiti dall'utente alla sezione < > del file di configurazione a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="8b66e-132">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
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
  
 <span data-ttu-id="8b66e-133">Quando il servizio viene inizializzato, il runtime di integrazione ricerca i tipi specificati e li aggiunge alla raccolta dei tipi noti per i contratti specificati.</span><span class="sxs-lookup"><span data-stu-id="8b66e-133">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b66e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b66e-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [<span data-ttu-id="8b66e-135">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="8b66e-135">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="8b66e-136">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="8b66e-136">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="8b66e-137">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="8b66e-137">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
