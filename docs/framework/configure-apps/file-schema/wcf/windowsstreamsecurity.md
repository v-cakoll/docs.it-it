---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 0f1dfd523e593c82727354db7ce39ffc992bdfb4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932798"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="4d57e-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="4d57e-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="4d57e-102">Specificare le impostazioni per la sicurezza del flusso di Windows dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4d57e-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="4d57e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4d57e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="4d57e-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="4d57e-104">\<bindings></span></span>  
<span data-ttu-id="4d57e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4d57e-105">\<customBinding></span></span>  
<span data-ttu-id="4d57e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="4d57e-106">\<binding></span></span>  
<span data-ttu-id="4d57e-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="4d57e-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d57e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d57e-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d57e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d57e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4d57e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d57e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d57e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d57e-111">Attributes</span></span>  
  
|<span data-ttu-id="4d57e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d57e-112">Attribute</span></span>|<span data-ttu-id="4d57e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d57e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d57e-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="4d57e-114">protectionLevel</span></span>|<span data-ttu-id="4d57e-115">Definisce la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="4d57e-115">Defines message-level security.</span></span> <span data-ttu-id="4d57e-116">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="4d57e-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="4d57e-117">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="4d57e-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="4d57e-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="4d57e-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4d57e-119">Nessuno Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="4d57e-119">-   None: No protection.</span></span><br /><span data-ttu-id="4d57e-120">Sign I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="4d57e-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="4d57e-121">EncryptAndSign I messaggi vengono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="4d57e-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="4d57e-122">L'impostazione predefinita è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="4d57e-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="4d57e-123">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="4d57e-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d57e-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d57e-124">Child Elements</span></span>  
 <span data-ttu-id="4d57e-125">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4d57e-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d57e-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d57e-126">Parent Elements</span></span>  
  
|<span data-ttu-id="4d57e-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d57e-127">Element</span></span>|<span data-ttu-id="4d57e-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d57e-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d57e-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="4d57e-129">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4d57e-130">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4d57e-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d57e-131">Note</span><span class="sxs-lookup"><span data-stu-id="4d57e-131">Remarks</span></span>  
 <span data-ttu-id="4d57e-132">I trasporti che usano un protocollo orientato al flusso, ad esempio TCP e named pipe, supportano aggiornamenti del trasporto basati sul flusso.</span><span class="sxs-lookup"><span data-stu-id="4d57e-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="4d57e-133">In particolare, WCF fornisce aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4d57e-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="4d57e-134">La configurazione di questa sicurezza del trasporto è incapsulata da questo elemento di configurazione, nonché da [ \<sslStreamSecurity >](sslstreamsecurity.md), che può essere configurato e aggiunto a un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="4d57e-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d57e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d57e-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="4d57e-136">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4d57e-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4d57e-137">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="4d57e-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4d57e-138">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4d57e-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4d57e-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4d57e-139">\<customBinding></span></span>](custombinding.md)
