---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: a73085320eaf248887422316e1b7787b8654d71d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400493"
---
# <a name="compositeduplex"></a><span data-ttu-id="7f5a9-101">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="7f5a9-101">\<compositeDuplex></span></span>
<span data-ttu-id="7f5a9-102">Definisce l'elemento di associazione usato quando il client deve esporre un endpoint affinché il servizio restituisca messaggi al client.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
<span data-ttu-id="7f5a9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f5a9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f5a9-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7f5a9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7f5a9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="7f5a9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7f5a9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="7f5a9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="7f5a9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="7f5a9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7f5a9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> compositeDuplex**</span><span class="sxs-lookup"><span data-stu-id="7f5a9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f5a9-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f5a9-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f5a9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f5a9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f5a9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f5a9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7f5a9-112">Attributes</span></span>  
  
|<span data-ttu-id="7f5a9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7f5a9-113">Attribute</span></span>|<span data-ttu-id="7f5a9-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f5a9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f5a9-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="7f5a9-115">clientBaseAddress</span></span>|<span data-ttu-id="7f5a9-116">URI che imposta l'indirizzo del canale di supporto in modalità duplex.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="7f5a9-117">Il servizio usa questo indirizzo per creare un contatto e stabilire una connessione con il client.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="7f5a9-118">Se questo attributo non è impostato, viene generato un indirizzo`full qualified name+default port\TemporaryIndigoAddress\guid`predefinito "".</span><span class="sxs-lookup"><span data-stu-id="7f5a9-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="7f5a9-119">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f5a9-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f5a9-120">Child Elements</span></span>  
 <span data-ttu-id="7f5a9-121">Nessuna</span><span class="sxs-lookup"><span data-stu-id="7f5a9-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f5a9-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f5a9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7f5a9-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f5a9-123">Element</span></span>|<span data-ttu-id="7f5a9-124">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f5a9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f5a9-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="7f5a9-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="7f5a9-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f5a9-127">Note</span><span class="sxs-lookup"><span data-stu-id="7f5a9-127">Remarks</span></span>  
 <span data-ttu-id="7f5a9-128">Questo elemento di configurazione viene usato con trasporti che non consentono comunicazioni duplex a livello nativo, ad esempio, HTTP.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="7f5a9-129">TCP, al contrario, consente comunicazioni duplex a livello nativo e non richiede l'uso di questo elemento di associazione affinché il servizio invii messaggi a un client.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="7f5a9-130">Il client deve esporre un indirizzo affinché il servizio crei un contatto e stabilisca una connessione.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="7f5a9-131">Questo indirizzo client è fornito dall'attributo `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="7f5a9-132">Si noti che Windows Communication Foundation (WCF) genera automaticamente un ClientBaseAddress se l'utente non ne imposta uno in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="7f5a9-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f5a9-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f5a9-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="7f5a9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f5a9-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="7f5a9-135">Associazioni</span><span class="sxs-lookup"><span data-stu-id="7f5a9-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7f5a9-136">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="7f5a9-136">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7f5a9-137">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="7f5a9-137">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7f5a9-138">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7f5a9-138">\<customBinding></span></span>](custombinding.md)
