---
title: '&lt;windowsStreamSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 5a0d3b61f473b49abdb2470a9fa5381dc9929274
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="91295-102">&lt;windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="91295-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="91295-103">Specificare le impostazioni per la sicurezza del flusso di Windows dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="91295-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="91295-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="91295-104">\<system.serviceModel></span></span>  
<span data-ttu-id="91295-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="91295-105">\<bindings></span></span>  
<span data-ttu-id="91295-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="91295-106">\<customBinding></span></span>  
<span data-ttu-id="91295-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="91295-107">\<binding></span></span>  
<span data-ttu-id="91295-108">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="91295-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91295-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91295-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91295-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91295-110">Attributes and Elements</span></span>  
 <span data-ttu-id="91295-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91295-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91295-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="91295-112">Attributes</span></span>  
  
|<span data-ttu-id="91295-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="91295-113">Attribute</span></span>|<span data-ttu-id="91295-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91295-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91295-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="91295-115">protectionLevel</span></span>|<span data-ttu-id="91295-116">Definisce la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="91295-116">Defines message-level security.</span></span> <span data-ttu-id="91295-117">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="91295-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="91295-118">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="91295-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="91295-119">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="91295-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="91295-120">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="91295-120">-   None: No protection.</span></span><br /><span data-ttu-id="91295-121">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="91295-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="91295-122">-EncryptAndSign: I messaggi sono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="91295-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="91295-123">L'impostazione predefinita è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="91295-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="91295-124">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="91295-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91295-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91295-125">Child Elements</span></span>  
 <span data-ttu-id="91295-126">None</span><span class="sxs-lookup"><span data-stu-id="91295-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91295-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91295-127">Parent Elements</span></span>  
  
|<span data-ttu-id="91295-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="91295-128">Element</span></span>|<span data-ttu-id="91295-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91295-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91295-130">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="91295-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="91295-131">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="91295-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91295-132">Note</span><span class="sxs-lookup"><span data-stu-id="91295-132">Remarks</span></span>  
 <span data-ttu-id="91295-133">I trasporti che usano un protocollo orientato al flusso, ad esempio TCP e named pipe, supportano aggiornamenti del trasporto basati sul flusso.</span><span class="sxs-lookup"><span data-stu-id="91295-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="91295-134">In particolare, WCF fornisce aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="91295-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="91295-135">La configurazione della sicurezza del trasporto viene incapsulata da questo elemento di configurazione, oltre che dalla [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), che possono essere configurati e aggiunto a un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="91295-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91295-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91295-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="91295-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="91295-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="91295-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="91295-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="91295-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="91295-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="91295-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="91295-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
