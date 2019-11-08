---
title: <transport> di <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735970"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="2ae2a-102">\<> di trasporto di \<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="2ae2a-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="2ae2a-103">Specifica le impostazioni per la sicurezza a livello di trasporto quando si usa il [\<> NetPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2ae2a-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="2ae2a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ae2a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2ae2a-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2ae2a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2ae2a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="2ae2a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="2ae2a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetPeerTcpBinding**](netpeertcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="2ae2a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="2ae2a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="2ae2a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2ae2a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**sicurezza**](security-of-netpeerbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="2ae2a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="2ae2a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport** ></span><span class="sxs-lookup"><span data-stu-id="2ae2a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae2a-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ae2a-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ae2a-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2ae2a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2ae2a-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2ae2a-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ae2a-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="2ae2a-114">Attributes</span></span>  
  
|<span data-ttu-id="2ae2a-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="2ae2a-115">Attribute</span></span>|<span data-ttu-id="2ae2a-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ae2a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ae2a-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="2ae2a-117">credentialType</span></span>|<span data-ttu-id="2ae2a-118">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2ae2a-118">Optional.</span></span> <span data-ttu-id="2ae2a-119">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="2ae2a-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="2ae2a-120">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="2ae2a-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="2ae2a-121">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="2ae2a-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="2ae2a-122">Value</span><span class="sxs-lookup"><span data-stu-id="2ae2a-122">Value</span></span>|<span data-ttu-id="2ae2a-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ae2a-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ae2a-124">Certificato</span><span class="sxs-lookup"><span data-stu-id="2ae2a-124">Certificate</span></span>|<span data-ttu-id="2ae2a-125">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="2ae2a-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="2ae2a-126">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2ae2a-126">Password</span></span>|<span data-ttu-id="2ae2a-127">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="2ae2a-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ae2a-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2ae2a-128">Child Elements</span></span>  
 <span data-ttu-id="2ae2a-129">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2ae2a-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ae2a-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2ae2a-130">Parent Elements</span></span>  
  
|<span data-ttu-id="2ae2a-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ae2a-131">Element</span></span>|<span data-ttu-id="2ae2a-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ae2a-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ae2a-133">\<security ></span><span class="sxs-lookup"><span data-stu-id="2ae2a-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="2ae2a-134">Definisce le impostazioni di sicurezza per il [\<> NetPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2ae2a-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ae2a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ae2a-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="2ae2a-136">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="2ae2a-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2ae2a-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="2ae2a-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2ae2a-138">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="2ae2a-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2ae2a-139">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="2ae2a-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2ae2a-140">\<binding ></span><span class="sxs-lookup"><span data-stu-id="2ae2a-140">\<binding></span></span>](bindings.md)
