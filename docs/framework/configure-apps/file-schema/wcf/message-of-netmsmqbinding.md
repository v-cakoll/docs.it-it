---
title: <message> di <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: b163dcb08e9656e3bde9c7fbb71fa1c92c9957ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931511"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="234de-102">\<> messaggi di \<NetMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="234de-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="234de-103">Definisce le impostazioni di sicurezza dei messaggi SOAP in questa associazione `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="234de-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="234de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="234de-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="234de-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="234de-105">Attributes and Elements</span></span>

<span data-ttu-id="234de-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="234de-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="234de-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="234de-107">Attributes</span></span>

|<span data-ttu-id="234de-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="234de-108">Attribute</span></span>|<span data-ttu-id="234de-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="234de-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="234de-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="234de-110">algorithmSuite</span></span>|<span data-ttu-id="234de-111">Imposta la crittografia del messaggio e gli algoritmi di incapsulamento della chiave usati per ottenere la sicurezza basata su messaggi per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="234de-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="234de-112">Il valore predefinito è `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="234de-112">The default value is `Aes256`.</span></span> <span data-ttu-id="234de-113">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="234de-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="234de-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="234de-114">clientCredentialType</span></span>|<span data-ttu-id="234de-115">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita per i messaggi inviati sul trasporto MSMQ.</span><span class="sxs-lookup"><span data-stu-id="234de-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="234de-116">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="234de-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="234de-117">Nessuno None: consente al servizio di interagire con i client anonimi.</span><span class="sxs-lookup"><span data-stu-id="234de-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="234de-118">Né il servizio né il client richiedono una credenziale.</span><span class="sxs-lookup"><span data-stu-id="234de-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="234de-119">Windows In questo modo gli scambi SOAP possono trovarsi nel contesto autenticato di una credenziale di Windows.</span><span class="sxs-lookup"><span data-stu-id="234de-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="234de-120">In questo caso viene sempre eseguita l'autenticazione basata su Kerberos.</span><span class="sxs-lookup"><span data-stu-id="234de-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="234de-121">Nome utente Ciò consente al servizio di richiedere che il client venga autenticato utilizzando una credenziale UserName.</span><span class="sxs-lookup"><span data-stu-id="234de-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="234de-122">In questo caso la credenziale deve essere specificata usando il `clientCredentials` comportamento **Attenzione:**  Windows Communication Foundation (WCF) non supporta l'invio di un digest della password o la derivazione di chiavi tramite password e l'utilizzo di tali chiavi per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="234de-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="234de-123">Pertanto, WCF impone che lo scambio sia protetto quando si utilizzano le credenziali del nome utente.</span><span class="sxs-lookup"><span data-stu-id="234de-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="234de-124">Questa modalità richiede che sia specificato il certificato del servizio sul lato client mediante il comportamento `clientCredential` e `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="234de-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="234de-125">Certificato Ciò consente al servizio di richiedere che il client venga autenticato tramite un certificato.</span><span class="sxs-lookup"><span data-stu-id="234de-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="234de-126">La credenziale client in questo caso deve essere specificata tramite il comportamento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="234de-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="234de-127">In questo caso la credenziale del servizio deve essere specificata usando il comportamento `clientCredentials` tramite la specifica di `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="234de-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="234de-128">CardSpace Ciò consente al servizio di richiedere che il client venga autenticato tramite CardSpace.</span><span class="sxs-lookup"><span data-stu-id="234de-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="234de-129">Il provisioning del certificato `serviceCertificate` deve essere eseguito nel comportamento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="234de-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="234de-130">Il valore predefinito è `Windows`.</span><span class="sxs-lookup"><span data-stu-id="234de-130">The default value is `Windows`.</span></span> <span data-ttu-id="234de-131">L'attributo è di tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="234de-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="234de-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="234de-132">Child Elements</span></span>

<span data-ttu-id="234de-133">Nessuna</span><span class="sxs-lookup"><span data-stu-id="234de-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="234de-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="234de-134">Parent Elements</span></span>

|<span data-ttu-id="234de-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="234de-135">Element</span></span>|<span data-ttu-id="234de-136">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="234de-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="234de-137">\<security></span><span class="sxs-lookup"><span data-stu-id="234de-137">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="234de-138">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="234de-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="234de-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="234de-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="234de-140">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="234de-140">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="234de-141">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="234de-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="234de-142">Associazioni</span><span class="sxs-lookup"><span data-stu-id="234de-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="234de-143">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="234de-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="234de-144">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="234de-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="234de-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="234de-145">\<binding></span></span>](../../../misc/binding.md)
