---
title: <security> di <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 2268bf48a2b86c3b3b25db006e6f8f55ea33af73
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738690"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="8191d-102">\<security> di \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="8191d-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="8191d-103">Definisce le impostazioni di sicurezza del trasporto per il canale di integrazione del servizio di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="8191d-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="8191d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8191d-104">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8191d-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8191d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8191d-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8191d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8191d-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="8191d-107">Attributes</span></span>  
  
|<span data-ttu-id="8191d-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="8191d-108">Attribute</span></span>|<span data-ttu-id="8191d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8191d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8191d-110">mode</span><span class="sxs-lookup"><span data-stu-id="8191d-110">mode</span></span>|<span data-ttu-id="8191d-111">Specifica il tipo di sicurezza che controlla integrità, riservatezza e autenticazione con il canale di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="8191d-111">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="8191d-112">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8191d-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8191d-113">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8191d-113">-   None: This disables security.</span></span><br /><span data-ttu-id="8191d-114">-Transport: la protezione e l'autenticazione sono offerte dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="8191d-114">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="8191d-115">Si applica alla sicurezza del messaggio tra i due gestori delle code.</span><span class="sxs-lookup"><span data-stu-id="8191d-115">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="8191d-116">Tra l'applicazione e il gestore della coda non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8191d-116">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="8191d-117">Le applicazioni Msmq esistenti sono funzionalmente equivalenti con questo tipo di modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8191d-117">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="8191d-118">Il valore predefinito è `Transport`.</span><span class="sxs-lookup"><span data-stu-id="8191d-118">The default value is `Transport`.</span></span> <span data-ttu-id="8191d-119">L'attributo è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8191d-119">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8191d-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8191d-120">Child Elements</span></span>  
  
|<span data-ttu-id="8191d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8191d-121">Element</span></span>|<span data-ttu-id="8191d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8191d-122">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="8191d-123">Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="8191d-123">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="8191d-124">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="8191d-124">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8191d-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8191d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8191d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="8191d-126">Element</span></span>|<span data-ttu-id="8191d-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8191d-127">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="8191d-128">Elemento di associazione di [\<msmqIntegrationBinding>](msmqintegrationbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="8191d-128">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8191d-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8191d-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="8191d-130">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="8191d-130">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="8191d-131">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="8191d-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8191d-132">Binding</span><span class="sxs-lookup"><span data-stu-id="8191d-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8191d-133">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="8191d-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8191d-134">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="8191d-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
