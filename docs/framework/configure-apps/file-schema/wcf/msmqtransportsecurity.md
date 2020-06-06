---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5899c609b3cf52c4a275ba6fb10c5826fcf37f1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153009"
---
# \<msmqTransportSecurity>
<span data-ttu-id="92460-101">Specifica le impostazioni di sicurezza del trasporto MSMQ di un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="92460-101">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="92460-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92460-102">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92460-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="92460-103">Attributes and Elements</span></span>  
 <span data-ttu-id="92460-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="92460-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92460-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="92460-105">Attributes</span></span>  
  
|<span data-ttu-id="92460-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="92460-106">Attribute</span></span>|<span data-ttu-id="92460-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92460-107">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="92460-108">Specifica come deve essere autenticato il messaggio dal trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="92460-108">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="92460-109">Se viene impostato su `None`, anche il valore dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.</span><span class="sxs-lookup"><span data-stu-id="92460-109">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="92460-110">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="92460-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="92460-111">-None: nessuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="92460-111">-   None: No authentication.</span></span><br /><span data-ttu-id="92460-112">-Windows: il meccanismo di autenticazione usa Active Directory per ottenere il certificato X. 509 per il SID associato al messaggio.</span><span class="sxs-lookup"><span data-stu-id="92460-112">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="92460-113">Questo viene quindi usato per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere nella coda.</span><span class="sxs-lookup"><span data-stu-id="92460-113">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="92460-114">-Certificate: il canale ottiene il certificato dall'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="92460-114">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="92460-115">L'impostazione predefinita è Windows.</span><span class="sxs-lookup"><span data-stu-id="92460-115">The default value is Windows.</span></span> <span data-ttu-id="92460-116">L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="92460-116">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="92460-117">Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="92460-117">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="92460-118">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="92460-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="92460-119">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="92460-119">-   RC4Stream</span></span><br /><span data-ttu-id="92460-120">-AES</span><span class="sxs-lookup"><span data-stu-id="92460-120">-   AES</span></span><br /><br /> <span data-ttu-id="92460-121">Il valore predefinito è RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="92460-121">The default value is RC4Stream.</span></span> <span data-ttu-id="92460-122">L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="92460-122">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="92460-123">Specifica come viene protetto il messaggio a livello del trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="92460-123">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="92460-124">La crittografia assicura l'integrità dei messaggi, mentre EncryptAndSign garantisce l'integrità e il non ripudio dei messaggi; ovvero, il messaggio deriva effettivamente dal mittente e il mittente è quello che dicono.</span><span class="sxs-lookup"><span data-stu-id="92460-124">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="92460-125">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="92460-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="92460-126">-None: nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="92460-126">-   None: No protection.</span></span><br /><span data-ttu-id="92460-127">-Sign: i messaggi sono firmati.</span><span class="sxs-lookup"><span data-stu-id="92460-127">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="92460-128">-EncryptAndSign: i messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="92460-128">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="92460-129">Il valore predefinito è Sign.</span><span class="sxs-lookup"><span data-stu-id="92460-129">The default value is Sign.</span></span> <span data-ttu-id="92460-130">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="92460-130">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="92460-131">Specifica l'algoritmo da usare nel calcolo del digest come parte delle firme.</span><span class="sxs-lookup"><span data-stu-id="92460-131">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="92460-132">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="92460-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="92460-133">-MD5</span><span class="sxs-lookup"><span data-stu-id="92460-133">-   MD5</span></span><br /><span data-ttu-id="92460-134">-SHA1</span><span class="sxs-lookup"><span data-stu-id="92460-134">-   SHA1</span></span><br /><span data-ttu-id="92460-135">-SHA256</span><span class="sxs-lookup"><span data-stu-id="92460-135">-   SHA256</span></span><br /><span data-ttu-id="92460-136">-SHA512</span><span class="sxs-lookup"><span data-stu-id="92460-136">-   SHA512</span></span><br /><br /> <span data-ttu-id="92460-137">Il valore predefinito è SHA1.</span><span class="sxs-lookup"><span data-stu-id="92460-137">The default value is SHA1.</span></span> <span data-ttu-id="92460-138">L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="92460-138">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="92460-139">A causa di problemi di collisione con MD5 e SHA1, Microsoft consiglia di SHA256 o meglio.</span><span class="sxs-lookup"><span data-stu-id="92460-139">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92460-140">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="92460-140">Child Elements</span></span>  
 <span data-ttu-id="92460-141">No.</span><span class="sxs-lookup"><span data-stu-id="92460-141">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92460-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="92460-142">Parent Elements</span></span>  
  
|<span data-ttu-id="92460-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="92460-143">Element</span></span>|<span data-ttu-id="92460-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92460-144">Description</span></span>|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|<span data-ttu-id="92460-145">Specifica le impostazioni necessarie per l'interazione con un mittente o un destinatario del sistema di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="92460-145">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[\<msmqTransport>](msmqtransport.md)|<span data-ttu-id="92460-146">Specifica le proprietà di comunicazione dell'accodamento per un servizio Windows Communication Foundation (WCF) che usa il protocollo MSMQ nativo.</span><span class="sxs-lookup"><span data-stu-id="92460-146">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92460-147">Commenti</span><span class="sxs-lookup"><span data-stu-id="92460-147">Remarks</span></span>  
 <span data-ttu-id="92460-148">Per ulteriori informazioni sulla sicurezza del trasporto, vedere [sicurezza del trasporto](../../../wcf/feature-details/transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="92460-148">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92460-149">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="92460-149">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="92460-150">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="92460-150">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="92460-151">Trasporti</span><span class="sxs-lookup"><span data-stu-id="92460-151">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="92460-152">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="92460-152">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="92460-153">Binding</span><span class="sxs-lookup"><span data-stu-id="92460-153">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="92460-154">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="92460-154">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="92460-155">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="92460-155">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="92460-156">Sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="92460-156">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
