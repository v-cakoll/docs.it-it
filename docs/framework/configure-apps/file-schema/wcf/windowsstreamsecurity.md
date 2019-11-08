---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735892"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="c0cd2-101">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="c0cd2-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="c0cd2-102">Specificare le impostazioni per la sicurezza del flusso di Windows dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="c0cd2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0cd2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c0cd2-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c0cd2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c0cd2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="c0cd2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="c0cd2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="c0cd2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c0cd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="c0cd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c0cd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="c0cd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0cd2-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0cd2-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0cd2-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c0cd2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c0cd2-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0cd2-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c0cd2-112">Attributes</span></span>  
  
|<span data-ttu-id="c0cd2-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c0cd2-113">Attribute</span></span>|<span data-ttu-id="c0cd2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0cd2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0cd2-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="c0cd2-115">protectionLevel</span></span>|<span data-ttu-id="c0cd2-116">Definisce la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-116">Defines message-level security.</span></span> <span data-ttu-id="c0cd2-117">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="c0cd2-118">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="c0cd2-119">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="c0cd2-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c0cd2-120">-None: nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-120">-   None: No protection.</span></span><br /><span data-ttu-id="c0cd2-121">-Sign: i messaggi sono firmati.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c0cd2-122">-EncryptAndSign: i messaggi sono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="c0cd2-123">L'impostazione predefinita è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="c0cd2-124">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0cd2-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c0cd2-125">Child Elements</span></span>  
 <span data-ttu-id="c0cd2-126">Nessuno</span><span class="sxs-lookup"><span data-stu-id="c0cd2-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0cd2-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c0cd2-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c0cd2-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0cd2-128">Element</span></span>|<span data-ttu-id="c0cd2-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0cd2-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0cd2-130">\<binding ></span><span class="sxs-lookup"><span data-stu-id="c0cd2-130">\<binding></span></span>](bindings.md)|<span data-ttu-id="c0cd2-131">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0cd2-132">Note</span><span class="sxs-lookup"><span data-stu-id="c0cd2-132">Remarks</span></span>  
 <span data-ttu-id="c0cd2-133">I trasporti che usano un protocollo orientato al flusso, ad esempio TCP e named pipe, supportano aggiornamenti del trasporto basati sul flusso.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="c0cd2-134">In particolare, WCF fornisce aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c0cd2-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="c0cd2-135">La configurazione di questa sicurezza del trasporto è incapsulata da questo elemento di configurazione, nonché da [\<> sslStreamSecurity](sslstreamsecurity.md), che può essere configurata e aggiunta a un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="c0cd2-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0cd2-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0cd2-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="c0cd2-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c0cd2-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c0cd2-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="c0cd2-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c0cd2-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c0cd2-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c0cd2-140">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="c0cd2-140">\<customBinding></span></span>](custombinding.md)
