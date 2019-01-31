---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: aff415bb75cf719ce19fb2189cc69c2c159af6cf
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281008"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="7171c-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="7171c-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="7171c-102">Specificare le impostazioni per la sicurezza del flusso di Windows dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7171c-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="7171c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7171c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="7171c-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="7171c-104">\<bindings></span></span>  
<span data-ttu-id="7171c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7171c-105">\<customBinding></span></span>  
<span data-ttu-id="7171c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="7171c-106">\<binding></span></span>  
<span data-ttu-id="7171c-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="7171c-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7171c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7171c-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7171c-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7171c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7171c-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7171c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7171c-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="7171c-111">Attributes</span></span>  
  
|<span data-ttu-id="7171c-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="7171c-112">Attribute</span></span>|<span data-ttu-id="7171c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7171c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7171c-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="7171c-114">protectionLevel</span></span>|<span data-ttu-id="7171c-115">Definisce la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="7171c-115">Defines message-level security.</span></span> <span data-ttu-id="7171c-116">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="7171c-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="7171c-117">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="7171c-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="7171c-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="7171c-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7171c-119">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="7171c-119">-   None: No protection.</span></span><br /><span data-ttu-id="7171c-120">-Accesso: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="7171c-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="7171c-121">-   EncryptAndSign: I messaggi sono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="7171c-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="7171c-122">L'impostazione predefinita è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="7171c-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="7171c-123">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="7171c-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7171c-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7171c-124">Child Elements</span></span>  
 <span data-ttu-id="7171c-125">nessuno</span><span class="sxs-lookup"><span data-stu-id="7171c-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7171c-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7171c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="7171c-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="7171c-127">Element</span></span>|<span data-ttu-id="7171c-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7171c-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7171c-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="7171c-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7171c-130">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7171c-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7171c-131">Note</span><span class="sxs-lookup"><span data-stu-id="7171c-131">Remarks</span></span>  
 <span data-ttu-id="7171c-132">I trasporti che usano un protocollo orientato al flusso, ad esempio TCP e named pipe, supportano aggiornamenti del trasporto basati sul flusso.</span><span class="sxs-lookup"><span data-stu-id="7171c-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="7171c-133">In particolare, WCF fornisce aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7171c-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="7171c-134">La configurazione di questa sicurezza del trasporto viene incapsulata da questo elemento di configurazione e dalla [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), che possono essere configurate e aggiunte a un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="7171c-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7171c-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7171c-135">See also</span></span>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="7171c-136">Associazioni</span><span class="sxs-lookup"><span data-stu-id="7171c-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7171c-137">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="7171c-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7171c-138">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="7171c-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7171c-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7171c-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
