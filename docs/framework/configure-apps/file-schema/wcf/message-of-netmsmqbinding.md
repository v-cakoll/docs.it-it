---
title: <message> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 060c7dc07e53d0114241ac7528a24363e78715c6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257180"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="6232a-102">\<messaggio > del \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="6232a-102">\<message> of \<netMsmqBinding></span></span>
<span data-ttu-id="6232a-103">Definisce le impostazioni di sicurezza dei messaggi SOAP in questa associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="6232a-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="6232a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6232a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6232a-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="6232a-105">\<bindings></span></span>  
<span data-ttu-id="6232a-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="6232a-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="6232a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="6232a-107">\<binding></span></span>  
<span data-ttu-id="6232a-108">\<security></span><span class="sxs-lookup"><span data-stu-id="6232a-108">\<security></span></span>  
<span data-ttu-id="6232a-109">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="6232a-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6232a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6232a-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6232a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6232a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6232a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6232a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6232a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="6232a-113">Attributes</span></span>  
  
|<span data-ttu-id="6232a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="6232a-114">Attribute</span></span>|<span data-ttu-id="6232a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6232a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6232a-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="6232a-116">algorithmSuite</span></span>|<span data-ttu-id="6232a-117">Imposta la crittografia del messaggio e gli algoritmi di incapsulamento della chiave usati per ottenere la sicurezza basata su messaggi per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6232a-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="6232a-118">Il valore predefinito è `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="6232a-118">The default value is `Aes256`.</span></span> <span data-ttu-id="6232a-119">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="6232a-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="6232a-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="6232a-120">clientCredentialType</span></span>|<span data-ttu-id="6232a-121">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6232a-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="6232a-122">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="6232a-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6232a-123">-None: None: consente al servizio di interagire con i client anonimi.</span><span class="sxs-lookup"><span data-stu-id="6232a-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="6232a-124">Né il servizio né il client richiedono una credenziale.</span><span class="sxs-lookup"><span data-stu-id="6232a-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="6232a-125">-   Windows: In questo modo l'esecuzione di scambi SOAP nel contesto autenticato di una credenziale Windows.</span><span class="sxs-lookup"><span data-stu-id="6232a-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="6232a-126">In questo caso viene sempre eseguita l'autenticazione basata su Kerberos.</span><span class="sxs-lookup"><span data-stu-id="6232a-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="6232a-127">-Nome utente: Ciò consente al servizio di richiedere che il client venga autenticato tramite una credenziale UserName.</span><span class="sxs-lookup"><span data-stu-id="6232a-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="6232a-128">La credenziale in questo caso deve essere specificata tramite il `clientCredentials` comportamento **cautela:**  Windows Communication Foundation (WCF) non supporta l'invio di un digest delle password o la derivazione delle chiavi utilizzano password e l'utilizzo di tali chiavi per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="6232a-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="6232a-129">WCF impone quindi che lo scambio sia protetto quando si usano credenziali UserName.</span><span class="sxs-lookup"><span data-stu-id="6232a-129">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="6232a-130">Questa modalità richiede che sia specificato il certificato del servizio sul lato client mediante il comportamento `clientCredential` e `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="6232a-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="6232a-131">-Certificato: Ciò consente al servizio di richiedere che il client venga autenticato tramite un certificato.</span><span class="sxs-lookup"><span data-stu-id="6232a-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="6232a-132">La credenziale client in questo caso deve essere specificata tramite il comportamento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="6232a-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="6232a-133">In questo caso la credenziale del servizio deve essere specificata usando il comportamento `clientCredentials` tramite la specifica di `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="6232a-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="6232a-134">-CardSpace: In questo modo il servizio di richiedere che il client venga autenticato tramite un CardSpace.</span><span class="sxs-lookup"><span data-stu-id="6232a-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="6232a-135">Il provisioning del certificato `serviceCertiifcate` deve essere eseguito nel comportamento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="6232a-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="6232a-136">Il valore predefinito è `Windows`.</span><span class="sxs-lookup"><span data-stu-id="6232a-136">The default value is `Windows`.</span></span> <span data-ttu-id="6232a-137">L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6232a-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6232a-138">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6232a-138">Child Elements</span></span>  
 <span data-ttu-id="6232a-139">nessuno</span><span class="sxs-lookup"><span data-stu-id="6232a-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6232a-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6232a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="6232a-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="6232a-141">Element</span></span>|<span data-ttu-id="6232a-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6232a-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6232a-143">\<security></span><span class="sxs-lookup"><span data-stu-id="6232a-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="6232a-144">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="6232a-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6232a-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6232a-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="6232a-146">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="6232a-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="6232a-147">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="6232a-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6232a-148">Associazioni</span><span class="sxs-lookup"><span data-stu-id="6232a-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6232a-149">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="6232a-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6232a-150">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="6232a-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6232a-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="6232a-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
