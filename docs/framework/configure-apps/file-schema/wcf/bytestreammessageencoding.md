---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 1d4109bde9c1668bc0832689b05e5d1dc3b198e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739057"
---
# \<byteStreamMessageEncoding>
<span data-ttu-id="85267-101">Specifica la codifica dei messaggi come flusso di byte, con l'opzione che consente di specificare la codifica dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="85267-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="85267-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85267-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85267-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="85267-103">Attributes and Elements</span></span>  
 <span data-ttu-id="85267-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="85267-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85267-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="85267-105">Attributes</span></span>  
  
|<span data-ttu-id="85267-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="85267-106">Attribute</span></span>|<span data-ttu-id="85267-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85267-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85267-108">messageVersion</span><span class="sxs-lookup"><span data-stu-id="85267-108">messageVersion</span></span>|<span data-ttu-id="85267-109">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="85267-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="85267-110">È possibile impostare questa proprietà solo sul valore relativo alla versione del messaggio <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="85267-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="85267-111">Il codificatore di messaggi del flusso di byte non supporta altre versioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="85267-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="85267-112">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="85267-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85267-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="85267-113">Child Elements</span></span>  
  
|<span data-ttu-id="85267-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="85267-114">Element</span></span>|<span data-ttu-id="85267-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85267-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="85267-116">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="85267-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="85267-117">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="85267-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85267-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="85267-118">Parent Elements</span></span>  
  
|<span data-ttu-id="85267-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="85267-119">Element</span></span>|<span data-ttu-id="85267-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85267-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="85267-121">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="85267-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85267-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="85267-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="85267-123">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="85267-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="85267-124">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="85267-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="85267-125">Binding</span><span class="sxs-lookup"><span data-stu-id="85267-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="85267-126">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="85267-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="85267-127">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="85267-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
