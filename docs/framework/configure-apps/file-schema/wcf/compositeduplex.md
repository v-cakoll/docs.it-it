---
title: '&lt;compositeDuplex&gt;'
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: e00cc6f3214dc9a040a9b6170271b1f4188d1631
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601623"
---
# <a name="ltcompositeduplexgt"></a><span data-ttu-id="f8f70-102">&lt;compositeDuplex&gt;</span><span class="sxs-lookup"><span data-stu-id="f8f70-102">&lt;compositeDuplex&gt;</span></span>
<span data-ttu-id="f8f70-103">Definisce l'elemento di associazione usato quando il client deve esporre un endpoint affinché il servizio restituisca messaggi al client.</span><span class="sxs-lookup"><span data-stu-id="f8f70-103">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="f8f70-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f8f70-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f8f70-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="f8f70-105">\<bindings></span></span>  
<span data-ttu-id="f8f70-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f8f70-106">\<customBinding></span></span>  
<span data-ttu-id="f8f70-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f8f70-107">\<binding></span></span>  
<span data-ttu-id="f8f70-108">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="f8f70-108">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f70-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8f70-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8f70-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8f70-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f8f70-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8f70-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8f70-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8f70-112">Attributes</span></span>  
  
|<span data-ttu-id="f8f70-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="f8f70-113">Attribute</span></span>|<span data-ttu-id="f8f70-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8f70-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8f70-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="f8f70-115">clientBaseAddress</span></span>|<span data-ttu-id="f8f70-116">URI che imposta l'indirizzo del canale di supporto in modalità duplex.</span><span class="sxs-lookup"><span data-stu-id="f8f70-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="f8f70-117">Il servizio usa questo indirizzo per creare un contatto e stabilire una connessione con il client.</span><span class="sxs-lookup"><span data-stu-id="f8f70-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="f8f70-118">Se questo attributo non è impostato, un indirizzo predefinito "`full qualified name+default port\TemporaryIndigoAddress\guid`" viene generato.</span><span class="sxs-lookup"><span data-stu-id="f8f70-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="f8f70-119">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="f8f70-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8f70-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8f70-120">Child Elements</span></span>  
 <span data-ttu-id="f8f70-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="f8f70-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8f70-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8f70-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f8f70-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8f70-123">Element</span></span>|<span data-ttu-id="f8f70-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8f70-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8f70-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="f8f70-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f8f70-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f8f70-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8f70-127">Note</span><span class="sxs-lookup"><span data-stu-id="f8f70-127">Remarks</span></span>  
 <span data-ttu-id="f8f70-128">Questo elemento di configurazione viene usato con trasporti che non consentono comunicazioni duplex a livello nativo, ad esempio, HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8f70-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="f8f70-129">TCP, al contrario, consente comunicazioni duplex a livello nativo e non richiede l'uso di questo elemento di associazione affinché il servizio invii messaggi a un client.</span><span class="sxs-lookup"><span data-stu-id="f8f70-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="f8f70-130">Il client deve esporre un indirizzo affinché il servizio crei un contatto e stabilisca una connessione.</span><span class="sxs-lookup"><span data-stu-id="f8f70-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="f8f70-131">Questo indirizzo client è fornito dall'attributo `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="f8f70-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="f8f70-132">Si noti che Windows Communication Foundation (WCF) genera automaticamente un ClientBaseAddress se l'utente non ne imposta uno in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="f8f70-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8f70-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8f70-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="f8f70-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8f70-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f8f70-135">Associazioni</span><span class="sxs-lookup"><span data-stu-id="f8f70-135">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f8f70-136">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="f8f70-136">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f8f70-137">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="f8f70-137">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f8f70-138">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f8f70-138">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
