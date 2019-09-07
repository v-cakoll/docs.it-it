---
title: <security> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: c780b157d0d566e24c6826c253401a51fbfab69d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399833"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="a862a-102">\<> di sicurezza \<di NetMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="a862a-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="a862a-103">Definisce le impostazioni di sicurezza per un'associazione MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a862a-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="a862a-104">e specifica se è stata abilitata la sicurezza basata sul trasporto o la sicurezza SOAP. In tal caso, indica la modalità di autenticazione e i livelli di protezione in uso.</span><span class="sxs-lookup"><span data-stu-id="a862a-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="a862a-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a862a-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a862a-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a862a-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a862a-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a862a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a862a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> NetMsmqBinding**](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a862a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="a862a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="a862a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a862a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="a862a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a862a-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a862a-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a862a-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a862a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a862a-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a862a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a862a-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="a862a-114">Attributes</span></span>  
  
|<span data-ttu-id="a862a-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="a862a-115">Attribute</span></span>|<span data-ttu-id="a862a-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a862a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a862a-117">modalità</span><span class="sxs-lookup"><span data-stu-id="a862a-117">mode</span></span>|<span data-ttu-id="a862a-118">Specifica il tipo di sicurezza che controlla integrità, riservatezza e autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a862a-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="a862a-119">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="a862a-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a862a-120">Nessuno Questa operazione Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a862a-120">-   None: This disables security.</span></span><br /><span data-ttu-id="a862a-121">Trasporto La protezione e l'autenticazione sono offerte dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="a862a-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="a862a-122">Si applica alla sicurezza del messaggio tra i due gestori delle code.</span><span class="sxs-lookup"><span data-stu-id="a862a-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="a862a-123">Tra l'applicazione e il gestore della coda non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a862a-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="a862a-124">Le applicazioni Msmq esistenti sono funzionalmente equivalenti con questo tipo di modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a862a-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="a862a-125">Messaggio Specifica la sicurezza dell'applicazione end-end.</span><span class="sxs-lookup"><span data-stu-id="a862a-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="a862a-126">A livello del trasporto non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a862a-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="a862a-127">È simile alla sicurezza offerta da altre associazioni standard.</span><span class="sxs-lookup"><span data-stu-id="a862a-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="a862a-128">Sia Offre sicurezza a livello di trasporto e messaggistica SOAP.</span><span class="sxs-lookup"><span data-stu-id="a862a-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="a862a-129">A entrambi i livelli è richiesta la stessa credenziale.</span><span class="sxs-lookup"><span data-stu-id="a862a-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="a862a-130">L'impostazione predefinita è Transport.</span><span class="sxs-lookup"><span data-stu-id="a862a-130">The default value is Transport.</span></span> <span data-ttu-id="a862a-131">L'attributo è di tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a862a-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a862a-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a862a-132">Child Elements</span></span>  
  
|<span data-ttu-id="a862a-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="a862a-133">Element</span></span>|<span data-ttu-id="a862a-134">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a862a-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a862a-135">\<> messaggi</span><span class="sxs-lookup"><span data-stu-id="a862a-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="a862a-136">Definisce le impostazioni di sicurezza per il messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="a862a-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="a862a-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="a862a-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="a862a-138">\<transport></span><span class="sxs-lookup"><span data-stu-id="a862a-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="a862a-139">Definisce le impostazioni di sicurezza per il trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a862a-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="a862a-140">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a862a-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a862a-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a862a-141">Parent Elements</span></span>  
  
|<span data-ttu-id="a862a-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="a862a-142">Element</span></span>|<span data-ttu-id="a862a-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a862a-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a862a-144">binding</span><span class="sxs-lookup"><span data-stu-id="a862a-144">binding</span></span>|<span data-ttu-id="a862a-145">Elemento di associazione di [ \<NetMsmqBinding >](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a862a-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a862a-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a862a-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="a862a-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="a862a-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a862a-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a862a-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a862a-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="a862a-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a862a-150">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="a862a-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a862a-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="a862a-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="a862a-152">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="a862a-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
