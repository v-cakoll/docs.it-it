---
title: '&lt;windowsStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
author: BrucePerlerMS
ms.openlocfilehash: 6c1253e6f402da6b818a4438142e122f8b31809c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193161"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="78cc4-102">&lt;windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="78cc4-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="78cc4-103">Specificare le impostazioni per la sicurezza del flusso di Windows dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="78cc4-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="78cc4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="78cc4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="78cc4-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="78cc4-105">\<bindings></span></span>  
<span data-ttu-id="78cc4-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="78cc4-106">\<customBinding></span></span>  
<span data-ttu-id="78cc4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="78cc4-107">\<binding></span></span>  
<span data-ttu-id="78cc4-108">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="78cc4-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78cc4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78cc4-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78cc4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="78cc4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78cc4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="78cc4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78cc4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="78cc4-112">Attributes</span></span>  
  
|<span data-ttu-id="78cc4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="78cc4-113">Attribute</span></span>|<span data-ttu-id="78cc4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78cc4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78cc4-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="78cc4-115">protectionLevel</span></span>|<span data-ttu-id="78cc4-116">Definisce la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="78cc4-116">Defines message-level security.</span></span> <span data-ttu-id="78cc4-117">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="78cc4-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="78cc4-118">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="78cc4-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="78cc4-119">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="78cc4-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="78cc4-120">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="78cc4-120">-   None: No protection.</span></span><br /><span data-ttu-id="78cc4-121">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="78cc4-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="78cc4-122">-EncryptAndSign: I messaggi sono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="78cc4-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="78cc4-123">L'impostazione predefinita è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="78cc4-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="78cc4-124">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="78cc4-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78cc4-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="78cc4-125">Child Elements</span></span>  
 <span data-ttu-id="78cc4-126">nessuno</span><span class="sxs-lookup"><span data-stu-id="78cc4-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78cc4-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="78cc4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="78cc4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="78cc4-128">Element</span></span>|<span data-ttu-id="78cc4-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78cc4-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78cc4-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="78cc4-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="78cc4-131">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="78cc4-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78cc4-132">Note</span><span class="sxs-lookup"><span data-stu-id="78cc4-132">Remarks</span></span>  
 <span data-ttu-id="78cc4-133">I trasporti che usano un protocollo orientato al flusso, ad esempio TCP e named pipe, supportano aggiornamenti del trasporto basati sul flusso.</span><span class="sxs-lookup"><span data-stu-id="78cc4-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="78cc4-134">In particolare, WCF fornisce aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="78cc4-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="78cc4-135">La configurazione di questa sicurezza del trasporto viene incapsulata da questo elemento di configurazione e dalla [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), che possono essere configurate e aggiunte a un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="78cc4-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78cc4-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78cc4-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="78cc4-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="78cc4-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="78cc4-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="78cc4-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="78cc4-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="78cc4-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="78cc4-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="78cc4-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
