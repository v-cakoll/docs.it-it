---
title: '&lt;security&gt; di &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 574c0d7cba88f724143e642da13cace8c329dea6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199994"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="1b59d-102">&lt;security&gt; di &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1b59d-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="1b59d-103">Definisce le impostazioni di sicurezza del trasporto per il canale di integrazione del servizio di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="1b59d-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="1b59d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1b59d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b59d-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1b59d-105">\<bindings></span></span>  
<span data-ttu-id="1b59d-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="1b59d-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="1b59d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b59d-107">\<binding></span></span>  
<span data-ttu-id="1b59d-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1b59d-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b59d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b59d-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b59d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1b59d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1b59d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1b59d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b59d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1b59d-112">Attributes</span></span>  
  
|<span data-ttu-id="1b59d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1b59d-113">Attribute</span></span>|<span data-ttu-id="1b59d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b59d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b59d-115">modalità</span><span class="sxs-lookup"><span data-stu-id="1b59d-115">mode</span></span>|<span data-ttu-id="1b59d-116">Specifica il tipo di sicurezza che controlla integrità, riservatezza e autenticazione con il canale di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="1b59d-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="1b59d-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="1b59d-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1b59d-118">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1b59d-118">-   None: This disables security.</span></span><br /><span data-ttu-id="1b59d-119">-Transport: La protezione e autenticazione sono offerte dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="1b59d-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="1b59d-120">Si applica alla sicurezza del messaggio tra i due gestori delle code.</span><span class="sxs-lookup"><span data-stu-id="1b59d-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="1b59d-121">Tra l'applicazione e il gestore della coda non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1b59d-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="1b59d-122">Le applicazioni Msmq esistenti sono funzionalmente equivalenti con questo tipo di modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1b59d-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="1b59d-123">Il valore predefinito è `Transport`.</span><span class="sxs-lookup"><span data-stu-id="1b59d-123">The default value is `Transport`.</span></span> <span data-ttu-id="1b59d-124">L'attributo è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="1b59d-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b59d-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1b59d-125">Child Elements</span></span>  
  
|<span data-ttu-id="1b59d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b59d-126">Element</span></span>|<span data-ttu-id="1b59d-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b59d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b59d-128">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="1b59d-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="1b59d-129">Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="1b59d-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="1b59d-130">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="1b59d-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b59d-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1b59d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="1b59d-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b59d-132">Element</span></span>|<span data-ttu-id="1b59d-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b59d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b59d-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b59d-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1b59d-135">L'elemento di associazione del [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1b59d-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b59d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b59d-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="1b59d-137">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="1b59d-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="1b59d-138">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="1b59d-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1b59d-139">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1b59d-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1b59d-140">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="1b59d-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1b59d-141">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="1b59d-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="1b59d-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b59d-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="1b59d-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="1b59d-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
