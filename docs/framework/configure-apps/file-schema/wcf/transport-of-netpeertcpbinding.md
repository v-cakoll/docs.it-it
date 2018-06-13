---
title: '&lt;transport&gt; di &lt;netPeerTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: c94336413424542f6fc6c0ef5b400b10ae715cd8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750700"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="9c75c-102">&lt;transport&gt; di &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9c75c-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="9c75c-103">Specifica le impostazioni di sicurezza a livello di trasporto quando si usa il [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9c75c-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="9c75c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9c75c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9c75c-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="9c75c-105">\<bindings></span></span>  
<span data-ttu-id="9c75c-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="9c75c-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="9c75c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9c75c-107">\<binding></span></span>  
<span data-ttu-id="9c75c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="9c75c-108">\<security></span></span>  
<span data-ttu-id="9c75c-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="9c75c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c75c-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c75c-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c75c-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9c75c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9c75c-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9c75c-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c75c-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="9c75c-113">Attributes</span></span>  
  
|<span data-ttu-id="9c75c-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="9c75c-114">Attribute</span></span>|<span data-ttu-id="9c75c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c75c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c75c-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="9c75c-116">credentialType</span></span>|<span data-ttu-id="9c75c-117">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9c75c-117">Optional.</span></span> <span data-ttu-id="9c75c-118">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="9c75c-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="9c75c-119">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9c75c-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="9c75c-120">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="9c75c-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="9c75c-121">Valore</span><span class="sxs-lookup"><span data-stu-id="9c75c-121">Value</span></span>|<span data-ttu-id="9c75c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c75c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9c75c-123">Certificato</span><span class="sxs-lookup"><span data-stu-id="9c75c-123">Certificate</span></span>|<span data-ttu-id="9c75c-124">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="9c75c-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="9c75c-125">Password</span><span class="sxs-lookup"><span data-stu-id="9c75c-125">Password</span></span>|<span data-ttu-id="9c75c-126">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="9c75c-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c75c-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9c75c-127">Child Elements</span></span>  
 <span data-ttu-id="9c75c-128">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9c75c-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c75c-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9c75c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="9c75c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c75c-130">Element</span></span>|<span data-ttu-id="9c75c-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c75c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c75c-132">\<security></span><span class="sxs-lookup"><span data-stu-id="9c75c-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="9c75c-133">Definisce le impostazioni di sicurezza per il [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9c75c-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c75c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c75c-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="9c75c-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9c75c-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9c75c-136">Associazioni</span><span class="sxs-lookup"><span data-stu-id="9c75c-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9c75c-137">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="9c75c-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9c75c-138">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9c75c-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9c75c-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="9c75c-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
