---
title: <message> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736753"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="9da96-102">messaggio di \<> di \<NetMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="9da96-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="9da96-103">Definisce le impostazioni di sicurezza dei messaggi SOAP in questa associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="9da96-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="9da96-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9da96-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9da96-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9da96-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9da96-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="9da96-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="9da96-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetMsmqBinding**](netmsmqbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="9da96-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="9da96-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="9da96-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9da96-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**sicurezza**](security-of-netmsmqbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="9da96-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="9da96-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**messaggio** ></span><span class="sxs-lookup"><span data-stu-id="9da96-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="9da96-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9da96-111">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9da96-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9da96-112">Attributes and Elements</span></span>

<span data-ttu-id="9da96-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9da96-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9da96-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="9da96-114">Attributes</span></span>

|<span data-ttu-id="9da96-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="9da96-115">Attribute</span></span>|<span data-ttu-id="9da96-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9da96-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="9da96-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9da96-117">algorithmSuite</span></span>|<span data-ttu-id="9da96-118">Imposta la crittografia del messaggio e gli algoritmi di incapsulamento della chiave usati per ottenere la sicurezza basata su messaggi per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9da96-118">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="9da96-119">Il valore predefinito è `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="9da96-119">The default value is `Aes256`.</span></span> <span data-ttu-id="9da96-120">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="9da96-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="9da96-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9da96-121">clientCredentialType</span></span>|<span data-ttu-id="9da96-122">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9da96-122">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="9da96-123">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="9da96-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9da96-124">-None: consente al servizio di interagire con client anonimi.</span><span class="sxs-lookup"><span data-stu-id="9da96-124">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="9da96-125">Né il servizio né il client richiedono una credenziale.</span><span class="sxs-lookup"><span data-stu-id="9da96-125">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="9da96-126">-Windows: consente di eseguire gli scambi SOAP nel contesto autenticato di una credenziale di Windows.</span><span class="sxs-lookup"><span data-stu-id="9da96-126">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="9da96-127">In questo caso viene sempre eseguita l'autenticazione basata su Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9da96-127">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="9da96-128">-UserName: consente al servizio di richiedere che il client venga autenticato utilizzando una credenziale UserName.</span><span class="sxs-lookup"><span data-stu-id="9da96-128">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="9da96-129">È necessario specificare le credenziali in questo caso utilizzando il comportamento `clientCredentials` **Attenzione:** Windows Communication Foundation (WCF) non supporta l'invio di un digest della password o la derivazione di chiavi utilizzando la password e l'utilizzo di tali chiavi per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9da96-129">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="9da96-130">Pertanto, WCF impone che lo scambio sia protetto quando si utilizzano le credenziali del nome utente.</span><span class="sxs-lookup"><span data-stu-id="9da96-130">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="9da96-131">Questa modalità richiede che sia specificato il certificato del servizio sul lato client mediante il comportamento `clientCredential` e `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="9da96-131">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="9da96-132">-Certificate: consente al servizio di richiedere che il client venga autenticato tramite un certificato.</span><span class="sxs-lookup"><span data-stu-id="9da96-132">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="9da96-133">La credenziale client in questo caso deve essere specificata tramite il comportamento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="9da96-133">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="9da96-134">In questo caso la credenziale del servizio deve essere specificata usando il comportamento `clientCredentials` tramite la specifica di `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="9da96-134">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="9da96-135">-CardSpace: consente al servizio di richiedere che il client venga autenticato tramite CardSpace.</span><span class="sxs-lookup"><span data-stu-id="9da96-135">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="9da96-136">Il provisioning del certificato `serviceCertificate` deve essere eseguito nel comportamento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="9da96-136">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="9da96-137">Il valore predefinito è `Windows`.</span><span class="sxs-lookup"><span data-stu-id="9da96-137">The default value is `Windows`.</span></span> <span data-ttu-id="9da96-138">L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9da96-138">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9da96-139">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9da96-139">Child Elements</span></span>

<span data-ttu-id="9da96-140">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9da96-140">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9da96-141">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9da96-141">Parent Elements</span></span>

|<span data-ttu-id="9da96-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="9da96-142">Element</span></span>|<span data-ttu-id="9da96-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9da96-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9da96-144">\<security ></span><span class="sxs-lookup"><span data-stu-id="9da96-144">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="9da96-145">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="9da96-145">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9da96-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9da96-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="9da96-147">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="9da96-147">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="9da96-148">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9da96-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9da96-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="9da96-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9da96-150">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="9da96-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9da96-151">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="9da96-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9da96-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="9da96-152">\<binding></span></span>](bindings.md)
