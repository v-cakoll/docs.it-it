---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735892"
---
# \<windowsStreamSecurity>
<span data-ttu-id="4c747-101">Specificare le impostazioni per la sicurezza del flusso di Windows dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4c747-101">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="4c747-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c747-102">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c747-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4c747-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4c747-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4c747-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c747-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="4c747-105">Attributes</span></span>  
  
|<span data-ttu-id="4c747-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="4c747-106">Attribute</span></span>|<span data-ttu-id="4c747-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c747-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c747-108">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="4c747-108">protectionLevel</span></span>|<span data-ttu-id="4c747-109">Definisce la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="4c747-109">Defines message-level security.</span></span> <span data-ttu-id="4c747-110">La firma dei messaggi riduce il rischio di manomissione del messaggio a opera di terze parti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="4c747-110">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="4c747-111">La crittografia garantisce la privacy a livello dei dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="4c747-111">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="4c747-112">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c747-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4c747-113">-None: nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="4c747-113">-   None: No protection.</span></span><br /><span data-ttu-id="4c747-114">-Sign: i messaggi sono firmati.</span><span class="sxs-lookup"><span data-stu-id="4c747-114">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="4c747-115">-EncryptAndSign: i messaggi sono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="4c747-115">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="4c747-116">L'impostazione predefinita è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="4c747-116">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="4c747-117">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="4c747-117">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c747-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4c747-118">Child Elements</span></span>  
 <span data-ttu-id="4c747-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="4c747-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c747-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4c747-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4c747-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c747-121">Element</span></span>|<span data-ttu-id="4c747-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c747-122">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="4c747-123">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4c747-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c747-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="4c747-124">Remarks</span></span>  
 <span data-ttu-id="4c747-125">I trasporti che usano un protocollo orientato al flusso, ad esempio TCP e named pipe, supportano aggiornamenti del trasporto basati sul flusso.</span><span class="sxs-lookup"><span data-stu-id="4c747-125">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="4c747-126">In particolare, WCF fornisce aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4c747-126">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="4c747-127">La configurazione di questa sicurezza del trasporto è incapsulata da questo elemento di configurazione, nonché da [\<sslStreamSecurity>](sslstreamsecurity.md) , che può essere configurato e aggiunto a un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="4c747-127">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c747-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4c747-128">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="4c747-129">Binding</span><span class="sxs-lookup"><span data-stu-id="4c747-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4c747-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="4c747-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4c747-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4c747-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
