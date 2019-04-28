---
title: <message> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: c623b7daf1e91c9c1800b9653525cd51b1087506
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768953"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="c68e7-102">\<messaggio > del \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="c68e7-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="c68e7-103">Definisce le impostazioni di sicurezza dei messaggi SOAP in questa associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="c68e7-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="c68e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c68e7-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="c68e7-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c68e7-105">Attributes and Elements</span></span>

<span data-ttu-id="c68e7-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c68e7-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c68e7-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c68e7-107">Attributes</span></span>

|<span data-ttu-id="c68e7-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="c68e7-108">Attribute</span></span>|<span data-ttu-id="c68e7-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c68e7-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="c68e7-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="c68e7-110">algorithmSuite</span></span>|<span data-ttu-id="c68e7-111">Imposta la crittografia del messaggio e gli algoritmi di incapsulamento della chiave usati per ottenere la sicurezza basata su messaggi per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c68e7-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="c68e7-112">Il valore predefinito è `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="c68e7-112">The default value is `Aes256`.</span></span> <span data-ttu-id="c68e7-113">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="c68e7-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="c68e7-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="c68e7-114">clientCredentialType</span></span>|<span data-ttu-id="c68e7-115">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c68e7-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="c68e7-116">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="c68e7-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c68e7-117">-None: None: consente al servizio di interagire con i client anonimi.</span><span class="sxs-lookup"><span data-stu-id="c68e7-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="c68e7-118">Né il servizio né il client richiedono una credenziale.</span><span class="sxs-lookup"><span data-stu-id="c68e7-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="c68e7-119">-   Windows: In questo modo l'esecuzione di scambi SOAP nel contesto autenticato di una credenziale Windows.</span><span class="sxs-lookup"><span data-stu-id="c68e7-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="c68e7-120">In questo caso viene sempre eseguita l'autenticazione basata su Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c68e7-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="c68e7-121">-Nome utente: Ciò consente al servizio di richiedere che il client venga autenticato tramite una credenziale UserName.</span><span class="sxs-lookup"><span data-stu-id="c68e7-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="c68e7-122">La credenziale in questo caso deve essere specificata tramite il `clientCredentials` comportamento **cautela:**  Windows Communication Foundation (WCF) non supporta l'invio di un digest delle password o la derivazione delle chiavi utilizzano password e l'utilizzo di tali chiavi per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="c68e7-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="c68e7-123">WCF impone quindi che lo scambio sia protetto quando si usano credenziali UserName.</span><span class="sxs-lookup"><span data-stu-id="c68e7-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="c68e7-124">Questa modalità richiede che sia specificato il certificato del servizio sul lato client mediante il comportamento `clientCredential` e `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="c68e7-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="c68e7-125">-Certificato: Ciò consente al servizio di richiedere che il client venga autenticato tramite un certificato.</span><span class="sxs-lookup"><span data-stu-id="c68e7-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="c68e7-126">La credenziale client in questo caso deve essere specificata tramite il comportamento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="c68e7-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="c68e7-127">In questo caso la credenziale del servizio deve essere specificata usando il comportamento `clientCredentials` tramite la specifica di `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="c68e7-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="c68e7-128">-CardSpace: In questo modo il servizio di richiedere che il client venga autenticato tramite un CardSpace.</span><span class="sxs-lookup"><span data-stu-id="c68e7-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="c68e7-129">Il provisioning del certificato `serviceCertificate` deve essere eseguito nel comportamento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="c68e7-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="c68e7-130">Il valore predefinito è `Windows`.</span><span class="sxs-lookup"><span data-stu-id="c68e7-130">The default value is `Windows`.</span></span> <span data-ttu-id="c68e7-131">L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="c68e7-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c68e7-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c68e7-132">Child Elements</span></span>

<span data-ttu-id="c68e7-133">nessuno</span><span class="sxs-lookup"><span data-stu-id="c68e7-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c68e7-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c68e7-134">Parent Elements</span></span>

|<span data-ttu-id="c68e7-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="c68e7-135">Element</span></span>|<span data-ttu-id="c68e7-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c68e7-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c68e7-137">\<security></span><span class="sxs-lookup"><span data-stu-id="c68e7-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="c68e7-138">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="c68e7-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c68e7-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c68e7-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="c68e7-140">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="c68e7-140">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="c68e7-141">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="c68e7-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c68e7-142">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c68e7-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c68e7-143">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="c68e7-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c68e7-144">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="c68e7-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c68e7-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="c68e7-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
