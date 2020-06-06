---
title: <message> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736753"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="e65a2-102">\<message> di \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="e65a2-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="e65a2-103">Definisce le impostazioni di sicurezza dei messaggi SOAP in questa associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="e65a2-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  

## <a name="syntax"></a><span data-ttu-id="e65a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e65a2-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e65a2-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e65a2-105">Attributes and Elements</span></span>

<span data-ttu-id="e65a2-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e65a2-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e65a2-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="e65a2-107">Attributes</span></span>

|<span data-ttu-id="e65a2-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="e65a2-108">Attribute</span></span>|<span data-ttu-id="e65a2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e65a2-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="e65a2-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="e65a2-110">algorithmSuite</span></span>|<span data-ttu-id="e65a2-111">Imposta la crittografia del messaggio e gli algoritmi di incapsulamento della chiave usati per ottenere la sicurezza basata su messaggi per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e65a2-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="e65a2-112">Il valore predefinito è `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="e65a2-112">The default value is `Aes256`.</span></span> <span data-ttu-id="e65a2-113">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="e65a2-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="e65a2-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e65a2-114">clientCredentialType</span></span>|<span data-ttu-id="e65a2-115">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e65a2-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="e65a2-116">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e65a2-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e65a2-117">-None: consente al servizio di interagire con client anonimi.</span><span class="sxs-lookup"><span data-stu-id="e65a2-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="e65a2-118">Né il servizio né il client richiedono una credenziale.</span><span class="sxs-lookup"><span data-stu-id="e65a2-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="e65a2-119">-Windows: consente di eseguire gli scambi SOAP nel contesto autenticato di una credenziale di Windows.</span><span class="sxs-lookup"><span data-stu-id="e65a2-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="e65a2-120">In questo caso viene sempre eseguita l'autenticazione basata su Kerberos.</span><span class="sxs-lookup"><span data-stu-id="e65a2-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="e65a2-121">-UserName: consente al servizio di richiedere che il client venga autenticato utilizzando una credenziale UserName.</span><span class="sxs-lookup"><span data-stu-id="e65a2-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="e65a2-122">In questo caso, le credenziali devono essere specificate utilizzando il `clientCredentials` comportamento **attenzione:** Windows Communication Foundation (WCF) non supporta l'invio di un digest della password o la derivazione di chiavi tramite password e l'utilizzo di tali chiavi per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="e65a2-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="e65a2-123">Quando si utilizzano credenziali di tipo NomeUtente WCF impone quindi che lo scambio venga protetto.</span><span class="sxs-lookup"><span data-stu-id="e65a2-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="e65a2-124">Questa modalità richiede che sia specificato il certificato del servizio sul lato client mediante il comportamento `clientCredential` e `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="e65a2-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="e65a2-125">-Certificate: consente al servizio di richiedere che il client venga autenticato tramite un certificato.</span><span class="sxs-lookup"><span data-stu-id="e65a2-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="e65a2-126">La credenziale client in questo caso deve essere specificata tramite il comportamento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="e65a2-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="e65a2-127">In questo caso la credenziale del servizio deve essere specificata usando il comportamento `clientCredentials` tramite la specifica di `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="e65a2-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="e65a2-128">-CardSpace: consente al servizio di richiedere che il client venga autenticato tramite CardSpace.</span><span class="sxs-lookup"><span data-stu-id="e65a2-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="e65a2-129">Il provisioning del certificato `serviceCertificate` deve essere eseguito nel comportamento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="e65a2-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="e65a2-130">Il valore predefinito è `Windows`.</span><span class="sxs-lookup"><span data-stu-id="e65a2-130">The default value is `Windows`.</span></span> <span data-ttu-id="e65a2-131">L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e65a2-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e65a2-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e65a2-132">Child Elements</span></span>

<span data-ttu-id="e65a2-133">nessuno</span><span class="sxs-lookup"><span data-stu-id="e65a2-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e65a2-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e65a2-134">Parent Elements</span></span>

|<span data-ttu-id="e65a2-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="e65a2-135">Element</span></span>|<span data-ttu-id="e65a2-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e65a2-136">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="e65a2-137">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="e65a2-137">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e65a2-138">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e65a2-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="e65a2-139">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="e65a2-139">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="e65a2-140">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="e65a2-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e65a2-141">Binding</span><span class="sxs-lookup"><span data-stu-id="e65a2-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e65a2-142">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="e65a2-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e65a2-143">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="e65a2-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
