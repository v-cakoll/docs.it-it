---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736785"
---
# \<compositeDuplex>
<span data-ttu-id="07aa4-101">Definisce l'elemento di associazione usato quando il client deve esporre un endpoint affinché il servizio restituisca messaggi al client.</span><span class="sxs-lookup"><span data-stu-id="07aa4-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="07aa4-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07aa4-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07aa4-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="07aa4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="07aa4-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="07aa4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07aa4-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="07aa4-105">Attributes</span></span>  
  
|<span data-ttu-id="07aa4-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="07aa4-106">Attribute</span></span>|<span data-ttu-id="07aa4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07aa4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07aa4-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="07aa4-108">clientBaseAddress</span></span>|<span data-ttu-id="07aa4-109">URI che imposta l'indirizzo del canale di supporto in modalità duplex.</span><span class="sxs-lookup"><span data-stu-id="07aa4-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="07aa4-110">Il servizio usa questo indirizzo per creare un contatto e stabilire una connessione con il client.</span><span class="sxs-lookup"><span data-stu-id="07aa4-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="07aa4-111">Se questo attributo non è impostato, viene generato un indirizzo predefinito " `full qualified name+default port\TemporaryIndigoAddress\guid` ".</span><span class="sxs-lookup"><span data-stu-id="07aa4-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="07aa4-112">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="07aa4-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07aa4-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="07aa4-113">Child Elements</span></span>  
 <span data-ttu-id="07aa4-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="07aa4-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07aa4-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="07aa4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="07aa4-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="07aa4-116">Element</span></span>|<span data-ttu-id="07aa4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07aa4-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="07aa4-118">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="07aa4-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07aa4-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="07aa4-119">Remarks</span></span>  
 <span data-ttu-id="07aa4-120">Questo elemento di configurazione viene usato con trasporti che non consentono comunicazioni duplex a livello nativo, ad esempio, HTTP.</span><span class="sxs-lookup"><span data-stu-id="07aa4-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="07aa4-121">TCP, al contrario, consente comunicazioni duplex a livello nativo e non richiede l'uso di questo elemento di associazione affinché il servizio invii messaggi a un client.</span><span class="sxs-lookup"><span data-stu-id="07aa4-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="07aa4-122">Il client deve esporre un indirizzo affinché il servizio crei un contatto e stabilisca una connessione.</span><span class="sxs-lookup"><span data-stu-id="07aa4-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="07aa4-123">Questo indirizzo client è fornito dall'attributo `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="07aa4-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="07aa4-124">Si noti che Windows Communication Foundation (WCF) genera automaticamente un ClientBaseAddress se l'utente non ne imposta uno in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="07aa4-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07aa4-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="07aa4-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="07aa4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07aa4-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="07aa4-127">Binding</span><span class="sxs-lookup"><span data-stu-id="07aa4-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="07aa4-128">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="07aa4-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="07aa4-129">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="07aa4-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
