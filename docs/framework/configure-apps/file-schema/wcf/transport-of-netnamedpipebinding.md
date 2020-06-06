---
title: <transport> di <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735967"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="6742b-102">\<transport> di \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="6742b-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="6742b-103">Definisce le impostazioni di sicurezza del trasporto per una named pipe.</span><span class="sxs-lookup"><span data-stu-id="6742b-103">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="6742b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6742b-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6742b-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6742b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6742b-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6742b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6742b-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="6742b-107">Attributes</span></span>  
  
|<span data-ttu-id="6742b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="6742b-108">Attribute</span></span>|<span data-ttu-id="6742b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6742b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6742b-110">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="6742b-110">protectionLevel</span></span>|<span data-ttu-id="6742b-111">Definisce il livello di protezione della named pipe.</span><span class="sxs-lookup"><span data-stu-id="6742b-111">Defines protection level of the named pipe.</span></span> <span data-ttu-id="6742b-112">La firma dei messaggi riduce il rischio di manomissione del messaggio a opera di terze parti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="6742b-112">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="6742b-113">La crittografia garantisce la privacy a livello dei dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="6742b-113">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="6742b-114">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6742b-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6742b-115">-None: nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="6742b-115">-   None: No protection.</span></span><br /><span data-ttu-id="6742b-116">-Sign: i messaggi sono firmati.</span><span class="sxs-lookup"><span data-stu-id="6742b-116">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="6742b-117">-EncryptAndSign: i messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="6742b-117">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="6742b-118">Il valore predefinito è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="6742b-118">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6742b-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6742b-119">Child Elements</span></span>  
 <span data-ttu-id="6742b-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="6742b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6742b-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6742b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6742b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="6742b-122">Element</span></span>|<span data-ttu-id="6742b-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6742b-123">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="6742b-124">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="6742b-124">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6742b-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6742b-125">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="6742b-126">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="6742b-126">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6742b-127">Binding</span><span class="sxs-lookup"><span data-stu-id="6742b-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6742b-128">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="6742b-128">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6742b-129">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="6742b-129">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
