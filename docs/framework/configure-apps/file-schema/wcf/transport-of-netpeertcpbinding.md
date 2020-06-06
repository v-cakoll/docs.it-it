---
title: <transport> di <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735970"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="81f70-102">\<transport> di \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="81f70-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="81f70-103">Specifica le impostazioni per la sicurezza a livello di trasporto quando si utilizza [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="81f70-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="81f70-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81f70-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81f70-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="81f70-105">Attributes and Elements</span></span>  
 <span data-ttu-id="81f70-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="81f70-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81f70-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="81f70-107">Attributes</span></span>  
  
|<span data-ttu-id="81f70-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="81f70-108">Attribute</span></span>|<span data-ttu-id="81f70-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81f70-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81f70-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="81f70-110">credentialType</span></span>|<span data-ttu-id="81f70-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="81f70-111">Optional.</span></span> <span data-ttu-id="81f70-112">Specifica il tipo di credenziali usate per verificare messaggi inviati con il trasporto peer.</span><span class="sxs-lookup"><span data-stu-id="81f70-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="81f70-113">L'attributo è di tipo <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="81f70-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="81f70-114">Attributo credentialType</span><span class="sxs-lookup"><span data-stu-id="81f70-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="81f70-115">Valore</span><span class="sxs-lookup"><span data-stu-id="81f70-115">Value</span></span>|<span data-ttu-id="81f70-116">Description</span><span class="sxs-lookup"><span data-stu-id="81f70-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="81f70-117">Certificato</span><span class="sxs-lookup"><span data-stu-id="81f70-117">Certificate</span></span>|<span data-ttu-id="81f70-118">L'autenticazione del trasporto del canale peer richiede un certificato X509.</span><span class="sxs-lookup"><span data-stu-id="81f70-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="81f70-119">Password</span><span class="sxs-lookup"><span data-stu-id="81f70-119">Password</span></span>|<span data-ttu-id="81f70-120">L'autenticazione del trasporto del canale peer richiede una password corretta.</span><span class="sxs-lookup"><span data-stu-id="81f70-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81f70-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="81f70-121">Child Elements</span></span>  
 <span data-ttu-id="81f70-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="81f70-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81f70-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="81f70-123">Parent Elements</span></span>  
  
|<span data-ttu-id="81f70-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="81f70-124">Element</span></span>|<span data-ttu-id="81f70-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81f70-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="81f70-126">Definisce le impostazioni di sicurezza per l'oggetto [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="81f70-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81f70-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="81f70-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="81f70-128">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="81f70-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="81f70-129">Binding</span><span class="sxs-lookup"><span data-stu-id="81f70-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="81f70-130">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="81f70-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="81f70-131">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="81f70-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
