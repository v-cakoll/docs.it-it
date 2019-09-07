---
title: <security> di <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: e4f10ab994429c6cbb690caef38114b8340e6839
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399859"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="a762c-102">\<> di sicurezza \<di MsmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="a762c-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="a762c-103">Definisce le impostazioni di sicurezza del trasporto per il canale di integrazione del servizio di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="a762c-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="a762c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a762c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a762c-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a762c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a762c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a762c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a762c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> msmqIntegrationBinding**](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a762c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="a762c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="a762c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a762c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="a762c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a762c-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a762c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a762c-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a762c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a762c-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a762c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a762c-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="a762c-113">Attributes</span></span>  
  
|<span data-ttu-id="a762c-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="a762c-114">Attribute</span></span>|<span data-ttu-id="a762c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a762c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a762c-116">modalità</span><span class="sxs-lookup"><span data-stu-id="a762c-116">mode</span></span>|<span data-ttu-id="a762c-117">Specifica il tipo di sicurezza che controlla integrità, riservatezza e autenticazione con il canale di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="a762c-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="a762c-118">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="a762c-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a762c-119">Nessuno Questa operazione Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a762c-119">-   None: This disables security.</span></span><br /><span data-ttu-id="a762c-120">Trasporto La protezione e l'autenticazione sono offerte dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="a762c-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="a762c-121">Si applica alla sicurezza del messaggio tra i due gestori delle code.</span><span class="sxs-lookup"><span data-stu-id="a762c-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="a762c-122">Tra l'applicazione e il gestore della coda non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a762c-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="a762c-123">Le applicazioni Msmq esistenti sono funzionalmente equivalenti con questo tipo di modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a762c-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="a762c-124">Il valore predefinito è `Transport`.</span><span class="sxs-lookup"><span data-stu-id="a762c-124">The default value is `Transport`.</span></span> <span data-ttu-id="a762c-125">L'attributo è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a762c-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a762c-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a762c-126">Child Elements</span></span>  
  
|<span data-ttu-id="a762c-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="a762c-127">Element</span></span>|<span data-ttu-id="a762c-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a762c-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a762c-129">\<transport></span><span class="sxs-lookup"><span data-stu-id="a762c-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="a762c-130">Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="a762c-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="a762c-131">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a762c-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a762c-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a762c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a762c-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="a762c-133">Element</span></span>|<span data-ttu-id="a762c-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a762c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a762c-135">\<binding></span><span class="sxs-lookup"><span data-stu-id="a762c-135">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="a762c-136">Elemento di associazione della [ \<> MsmqIntegrationBinding](msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a762c-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a762c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a762c-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="a762c-138">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="a762c-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="a762c-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="a762c-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a762c-140">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a762c-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a762c-141">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="a762c-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a762c-142">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="a762c-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a762c-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="a762c-143">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="a762c-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="a762c-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
