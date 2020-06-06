---
title: <transport> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152931"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="ef547-102">\<transport> di \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="ef547-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="ef547-103">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="ef547-103">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="ef547-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef547-104">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef547-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef547-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ef547-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef547-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef547-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef547-107">Attributes</span></span>  
  
|<span data-ttu-id="ef547-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ef547-108">Attribute</span></span>|<span data-ttu-id="ef547-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef547-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef547-110">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="ef547-110">msmqAuthenticationMode</span></span>|<span data-ttu-id="ef547-111">Specifica come deve essere autenticato il messaggio dal trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ef547-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="ef547-112">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef547-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ef547-113">-None: nessuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ef547-113">-   None: No authentication.</span></span><br /><span data-ttu-id="ef547-114">-WindowsDomain: il meccanismo di autenticazione usa Active Directory per recuperare il certificato X. 509 per l'identificatore di sicurezza associato al messaggio.</span><span class="sxs-lookup"><span data-stu-id="ef547-114">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="ef547-115">Questo viene quindi utilizzo per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere sulla coda.</span><span class="sxs-lookup"><span data-stu-id="ef547-115">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="ef547-116">-Certificate: il canale Recupera il certificato dall'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="ef547-116">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="ef547-117">Il valore predefinito è `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="ef547-117">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="ef547-118">Se questo attributo viene impostato su `None`, anche l'attributo dell'attributo `msmqProtectionLevel` deve essere impostato su `None`.</span><span class="sxs-lookup"><span data-stu-id="ef547-118">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="ef547-119">L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="ef547-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="ef547-120">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="ef547-120">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="ef547-121">Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ef547-121">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="ef547-122">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef547-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ef547-123">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="ef547-123">-   RC4Stream</span></span><br /><span data-ttu-id="ef547-124">-AES</span><span class="sxs-lookup"><span data-stu-id="ef547-124">-   AES</span></span><br /><span data-ttu-id="ef547-125">-Il valore predefinito è `RC4Stream` .</span><span class="sxs-lookup"><span data-stu-id="ef547-125">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="ef547-126">L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="ef547-126">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="ef547-127">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="ef547-127">msmqProtectionLevel</span></span>|<span data-ttu-id="ef547-128">Specifica il metodo di sicurezza dei messaggi al livello del trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ef547-128">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="ef547-129">La crittografia assicura l'integrità del messaggio, mentre la firma e la crittografa assicurano l'integrità del messaggio e il non ripudio.</span><span class="sxs-lookup"><span data-stu-id="ef547-129">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="ef547-130">Ovvero, il messaggio proviene effettivamente dal mittente e il mittente è quello che dicono.</span><span class="sxs-lookup"><span data-stu-id="ef547-130">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="ef547-131">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef547-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ef547-132">-None: nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="ef547-132">-   None: No protection.</span></span><br /><span data-ttu-id="ef547-133">-Sign: i messaggi sono firmati.</span><span class="sxs-lookup"><span data-stu-id="ef547-133">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ef547-134">-EncryptAndSign: i messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="ef547-134">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="ef547-135">-Il valore predefinito è `Sign` .</span><span class="sxs-lookup"><span data-stu-id="ef547-135">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="ef547-136">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="ef547-136">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="ef547-137">Specifica l'algoritmo hash da usare per il calcolo del digest del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ef547-137">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="ef547-138">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef547-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ef547-139">-MD5</span><span class="sxs-lookup"><span data-stu-id="ef547-139">-   MD5</span></span><br /><span data-ttu-id="ef547-140">-SHA1</span><span class="sxs-lookup"><span data-stu-id="ef547-140">-   SHA1</span></span><br /><span data-ttu-id="ef547-141">-SHA256</span><span class="sxs-lookup"><span data-stu-id="ef547-141">-   SHA256</span></span><br /><span data-ttu-id="ef547-142">-SHA512</span><span class="sxs-lookup"><span data-stu-id="ef547-142">-   SHA512</span></span><br /><br /> <span data-ttu-id="ef547-143">Il valore predefinito è `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="ef547-143">The default is `SHA1`.</span></span> <span data-ttu-id="ef547-144">L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="ef547-144">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="ef547-145">A causa di problemi di collisione con MD5 e SHA1, Microsoft consiglia di SHA256 o meglio.</span><span class="sxs-lookup"><span data-stu-id="ef547-145">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef547-146">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef547-146">Child Elements</span></span>  
 <span data-ttu-id="ef547-147">nessuno</span><span class="sxs-lookup"><span data-stu-id="ef547-147">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef547-148">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef547-148">Parent Elements</span></span>  
  
|<span data-ttu-id="ef547-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef547-149">Element</span></span>|<span data-ttu-id="ef547-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef547-150">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="ef547-151">Definisce le impostazioni di sicurezza del trasporto per i trasporti in coda.</span><span class="sxs-lookup"><span data-stu-id="ef547-151">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef547-152">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ef547-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="ef547-153">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="ef547-153">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="ef547-154">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="ef547-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ef547-155">Binding</span><span class="sxs-lookup"><span data-stu-id="ef547-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ef547-156">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="ef547-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ef547-157">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="ef547-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
