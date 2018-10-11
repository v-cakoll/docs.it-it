---
title: 'Procedura: creare un servizio token di sicurezza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 98e82101-4cff-4bb8-a220-f7abed3556e5
author: BrucePerlerMS
ms.openlocfilehash: 6dbf0e2be0a75fccd84a82fe2b3c8ab41762de83
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087726"
---
# <a name="how-to-create-a-security-token-service"></a><span data-ttu-id="838e6-102">Procedura: creare un servizio token di sicurezza</span><span class="sxs-lookup"><span data-stu-id="838e6-102">How to: Create a Security Token Service</span></span>
<span data-ttu-id="838e6-103">Un servizio token di sicurezza implementa il protocollo definito nella specifica WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="838e6-103">A security token service implements the protocol defined in the WS-Trust specification.</span></span> <span data-ttu-id="838e6-104">Questo protocollo definisce i formati e i modelli di scambio dei messaggi per il rilascio, il rinnovo, l'annullamento e la convalida di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="838e6-104">This protocol defines message formats and message exchange patterns for issuing, renewing, canceling, and validating security tokens.</span></span> <span data-ttu-id="838e6-105">Un determinato servizio token di sicurezza fornisce una o più di queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="838e6-105">A given security token service provides one or more of these capabilities.</span></span> <span data-ttu-id="838e6-106">In questo argomento viene descritto lo scenario più comune: l'implementazione del rilascio di token.</span><span class="sxs-lookup"><span data-stu-id="838e6-106">This topic looks at the most common scenario: implementing token issuance.</span></span>  
  
## <a name="issuing-tokens"></a><span data-ttu-id="838e6-107">Rilascio di token</span><span class="sxs-lookup"><span data-stu-id="838e6-107">Issuing Tokens</span></span>  
 <span data-ttu-id="838e6-108">Per l'esecuzione del rilascio del token WS-Trust definisce i formati dei messaggi in base all'elemento dello schema XSD (XML Schema Definition Language) di `RequestSecurityToken` e all'elemento dello schema XSD di `RequestSecurityTokenResponse`.</span><span class="sxs-lookup"><span data-stu-id="838e6-108">WS-Trust defines message formats, based on the `RequestSecurityToken` XML Schema definition language (XSD) schema element, and `RequestSecurityTokenResponse` XSD schema element for performing token issuance.</span></span> <span data-ttu-id="838e6-109">Definisce inoltre gli URI (Uniform Resource Identifiers) dell'azione associati.</span><span class="sxs-lookup"><span data-stu-id="838e6-109">In addition, it defines the associated Action Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="838e6-110">L'azione associata all'URI con il `RequestSecurityToken` messaggio `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`.</span><span class="sxs-lookup"><span data-stu-id="838e6-110">The action URI associated with the `RequestSecurityToken` message is `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`.</span></span> <span data-ttu-id="838e6-111">L'azione associata all'URI con il `RequestSecurityTokenResponse` messaggio `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`.</span><span class="sxs-lookup"><span data-stu-id="838e6-111">The action URI associated with the `RequestSecurityTokenResponse` message is   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`.</span></span>  
  
### <a name="request-message-structure"></a><span data-ttu-id="838e6-112">Struttura del messaggio di richiesta</span><span class="sxs-lookup"><span data-stu-id="838e6-112">Request Message Structure</span></span>  
 <span data-ttu-id="838e6-113">In genere la struttura del messaggio di richiesta consiste negli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="838e6-113">The issue request message structure typically consists of the following items:</span></span>  
  
-   <span data-ttu-id="838e6-114">Una richiesta di digitare l'URI con un valore di `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`.</span><span class="sxs-lookup"><span data-stu-id="838e6-114">A request type URI with a value of `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`.</span></span>
  
-   <span data-ttu-id="838e6-115">Un URI di tipo token.</span><span class="sxs-lookup"><span data-stu-id="838e6-115">A token type URI.</span></span> <span data-ttu-id="838e6-116">Per i token Security Assertions Markup Language (SAML) 1.1, il valore di questo URI è `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`.</span><span class="sxs-lookup"><span data-stu-id="838e6-116">For Security Assertions Markup Language (SAML) 1.1 tokens, the value of this URI is `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`.</span></span>  
  
-   <span data-ttu-id="838e6-117">Un valore della dimensione della chiave che indica il numero di bit nella chiave da associare al token rilasciato.</span><span class="sxs-lookup"><span data-stu-id="838e6-117">A key size value that indicates the number of bits in the key to be associated with the issued token.</span></span>  
  
-   <span data-ttu-id="838e6-118">Un URI di tipo chiave.</span><span class="sxs-lookup"><span data-stu-id="838e6-118">A key type URI.</span></span> <span data-ttu-id="838e6-119">Per le chiavi simmetriche, il valore di questo URI è `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="838e6-119">For symmetric keys, the value of this URI is `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey`.</span></span>  
  
 <span data-ttu-id="838e6-120">Potrebbero inoltre essere presenti altri elementi:</span><span class="sxs-lookup"><span data-stu-id="838e6-120">In addition, a couple of other items might be present:</span></span>  
  
-   <span data-ttu-id="838e6-121">Materiale della chiave fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="838e6-121">Key material provided by the client.</span></span>  
  
-   <span data-ttu-id="838e6-122">Informazioni di ambito che indicano il servizio di destinazione con il quale verrà utilizzato il token rilasciato.</span><span class="sxs-lookup"><span data-stu-id="838e6-122">Scope information that indicates the target service that the issued token will be used with.</span></span>  
  
 <span data-ttu-id="838e6-123">Il servizio token di sicurezza utilizza le informazioni contenute nel messaggio di richiesta di rilascio quando costruisce il messaggio di risposta del rilascio.</span><span class="sxs-lookup"><span data-stu-id="838e6-123">The security token service uses the information in the issue request message when it constructs the Issue Response message.</span></span>  
  
## <a name="response-message-structure"></a><span data-ttu-id="838e6-124">Struttura del messaggio di risposta</span><span class="sxs-lookup"><span data-stu-id="838e6-124">Response Message Structure</span></span>  
 <span data-ttu-id="838e6-125">In genere la struttura del messaggio di risposta consiste negli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="838e6-125">The issue response message structure typically consists of the following items;</span></span>  
  
-   <span data-ttu-id="838e6-126">Token di sicurezza rilasciato, ad esempio un'asserzione SAML 1.1.</span><span class="sxs-lookup"><span data-stu-id="838e6-126">The issued security token, for example, a SAML 1.1 assertion.</span></span>  
  
-   <span data-ttu-id="838e6-127">Token di prova associato al token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="838e6-127">A proof token associated with the security token.</span></span> <span data-ttu-id="838e6-128">Per le chiavi simmetriche spesso si tratta della forma crittografata del materiale della chiave.</span><span class="sxs-lookup"><span data-stu-id="838e6-128">For symmetric keys, this is often an encrypted form of the key material.</span></span>  
  
-   <span data-ttu-id="838e6-129">Riferimenti al token di sicurezza rilasciato.</span><span class="sxs-lookup"><span data-stu-id="838e6-129">References to the issued security token.</span></span> <span data-ttu-id="838e6-130">In genere, il servizio token di sicurezza restituisce un riferimento che può essere utilizzato quando il token rilasciato ricorre in un messaggio successivo inviato dal client e un altro riferimento che può essere utilizzato quando il token non è presente nei messaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="838e6-130">Typically, the security token service returns a reference that can be used when the issued token appears in a subsequent message sent by the client and another that can be used when the token is not present in subsequent messages.</span></span>  
  
 <span data-ttu-id="838e6-131">Potrebbero inoltre essere presenti altri elementi:</span><span class="sxs-lookup"><span data-stu-id="838e6-131">In addition, a couple of other items might be present:</span></span>  
  
-   <span data-ttu-id="838e6-132">Materiale della chiave fornito dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="838e6-132">Key material provided by the security token service.</span></span>  
  
-   <span data-ttu-id="838e6-133">Algoritmo necessario per calcolare la chiave condivisa.</span><span class="sxs-lookup"><span data-stu-id="838e6-133">The algorithm needed to compute the shared key.</span></span>  
  
-   <span data-ttu-id="838e6-134">Informazioni sulla durata per il token rilasciato.</span><span class="sxs-lookup"><span data-stu-id="838e6-134">Lifetime information for the issued token.</span></span>  
  
## <a name="processing-request-messages"></a><span data-ttu-id="838e6-135">Elaborazione dei messaggi di richiesta</span><span class="sxs-lookup"><span data-stu-id="838e6-135">Processing Request Messages</span></span>  
 <span data-ttu-id="838e6-136">Il servizio token di sicurezza elabora la richiesta di rilascio esaminando i vari elementi del messaggio di richiesta e valutando la possibilità di rilasciare un token che soddisfi la richiesta.</span><span class="sxs-lookup"><span data-stu-id="838e6-136">The security token service processes the issue request by examining the various pieces of the request message and ensuring that it can issue a token that satisfies the request.</span></span> <span data-ttu-id="838e6-137">Il servizio token di sicurezza deve determinare quanto segue prima di costruire il token da rilasciare:</span><span class="sxs-lookup"><span data-stu-id="838e6-137">The security token service must determine the following before it constructs the token to be issued:</span></span>  
  
-   <span data-ttu-id="838e6-138">La richiesta riguarda effettivamente il rilascio di un token.</span><span class="sxs-lookup"><span data-stu-id="838e6-138">The request really is a request for a token to be issued.</span></span>  
  
-   <span data-ttu-id="838e6-139">Il servizio token di sicurezza supporta il tipo di token richiesto.</span><span class="sxs-lookup"><span data-stu-id="838e6-139">The security token service supports the requested token type.</span></span>  
  
-   <span data-ttu-id="838e6-140">Il richiedente è autorizzato a eseguire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="838e6-140">The requester is authorized to make the request.</span></span>  
  
-   <span data-ttu-id="838e6-141">Il servizio token di sicurezza può soddisfare le aspettative del richiedente in merito al materiale della chiave.</span><span class="sxs-lookup"><span data-stu-id="838e6-141">The security token service can meet the requester's expectations with respect to key material.</span></span>  
  
 <span data-ttu-id="838e6-142">Due punti fondamentali nella costruzione di un token consistono nello stabilire la chiave con la quale firmare il token e la chiave con la quale crittografare la chiave condivisa.</span><span class="sxs-lookup"><span data-stu-id="838e6-142">Two vital parts of constructing a token are determining what key to sign the token with and what key to encrypt the shared key with.</span></span> <span data-ttu-id="838e6-143">È necessario che il token venga firmato affinché, quando il client presenta il token al servizio di destinazione, quest'ultimo sia in grado di appurare che il token è stato rilasciato da un servizio token di sicurezza affidabile.</span><span class="sxs-lookup"><span data-stu-id="838e6-143">The token needs to be signed so that when the client presents the token to the target service, that service can determine that the token was issued by a security token service that it trusts.</span></span> <span data-ttu-id="838e6-144">Il materiale della chiave deve essere crittografato in modo tale da consentire al servizio di destinazione di decrittografarlo.</span><span class="sxs-lookup"><span data-stu-id="838e6-144">The key material needs to be encrypted in such a way that the target service can decrypt that key material.</span></span>  
  
 <span data-ttu-id="838e6-145">La firma di un'asserzione SAML implica la creazione di un'istanza <xref:System.IdentityModel.Tokens.SigningCredentials>.</span><span class="sxs-lookup"><span data-stu-id="838e6-145">Signing a SAML assertion involves creating a <xref:System.IdentityModel.Tokens.SigningCredentials> instance.</span></span> <span data-ttu-id="838e6-146">Il costruttore di questa classe accetta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="838e6-146">The constructor for this class takes the following:</span></span>  
  
-   <span data-ttu-id="838e6-147">Un elemento <xref:System.IdentityModel.Tokens.SecurityKey> che la chiave utilizza per firmare l'asserzione SAML.</span><span class="sxs-lookup"><span data-stu-id="838e6-147">A <xref:System.IdentityModel.Tokens.SecurityKey> for the key to use to sign the SAML assertion.</span></span>  
  
-   <span data-ttu-id="838e6-148">Una stringa che identifica l'algoritmo della firma da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="838e6-148">A string identifying the signature algorithm to use.</span></span>  
  
-   <span data-ttu-id="838e6-149">Una stringa che identifica l'algoritmo di digest da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="838e6-149">A string identifying the digest algorithm to use.</span></span>  
  
-   <span data-ttu-id="838e6-150">Facoltativamente un elemento <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> che identifica la chiave da utilizzare per firmare l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="838e6-150">Optionally, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> that identifies the key to use to sign the assertion.</span></span>  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 <span data-ttu-id="838e6-151">La crittografia della chiave condivisa comporta la crittografia del materiale della chiave con una chiave che il servizio di destinazione può utilizzare per decrittografare la chiave condivisa.</span><span class="sxs-lookup"><span data-stu-id="838e6-151">Encrypting the shared key involves taking the key material and encrypting it with a key that the target service can use to decrypt the shared key.</span></span> <span data-ttu-id="838e6-152">In genere viene utilizzata la chiave pubblica del servizio di destinazione.</span><span class="sxs-lookup"><span data-stu-id="838e6-152">Typically, the public key of the target service is used.</span></span>  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 <span data-ttu-id="838e6-153">È inoltre necessario un elemento <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> per la chiave crittografata.</span><span class="sxs-lookup"><span data-stu-id="838e6-153">In addition, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> for the encrypted key is needed.</span></span>  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 <span data-ttu-id="838e6-154">L'oggetto <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> viene quindi utilizzato per creare `SamlSubject` come parte di `SamlToken`.</span><span class="sxs-lookup"><span data-stu-id="838e6-154">This <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> is then used to create a `SamlSubject` as part of the `SamlToken`.</span></span>  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 <span data-ttu-id="838e6-155">Per altre informazioni, vedere [esempio di federazione](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="838e6-155">For more information, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="creating-response-messages"></a><span data-ttu-id="838e6-156">Creazione dei messaggi di risposta</span><span class="sxs-lookup"><span data-stu-id="838e6-156">Creating Response Messages</span></span>  
 <span data-ttu-id="838e6-157">Terminata l'elaborazione della richiesta di rilascio da parte del servizio token di sicurezza e conclusa la costruzione del token da rilasciare unitamente alla chiave di prova, è necessario costruire il messaggio di risposta, che deve comprendere almeno il token richiesto, il token di prova e i riferimenti del token rilasciato.</span><span class="sxs-lookup"><span data-stu-id="838e6-157">Once the security token service processes the issue request and constructs the token to be issued along with the proof key, the response message needs to be constructed, including at least the requested token, the proof token, and the issued token references.</span></span> <span data-ttu-id="838e6-158">Il token rilasciato è in genere un <xref:System.IdentityModel.Tokens.SamlSecurityToken> creato da <xref:System.IdentityModel.Tokens.SamlAssertion>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="838e6-158">The issued token is typically a <xref:System.IdentityModel.Tokens.SamlSecurityToken> created from the <xref:System.IdentityModel.Tokens.SamlAssertion>, as shown in the following example.</span></span>  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 <span data-ttu-id="838e6-159">Nel caso in cui il servizio token di sicurezza fornisca il materiale della chiave condivisa, il token di prova viene costruito creando un elemento <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="838e6-159">In the case where the security token service provides the shared key material, the proof token is constructed by creating a <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span></span>  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 <span data-ttu-id="838e6-160">Per altre informazioni su come costruire il token di prova quando il client e servizio token di sicurezza fornisce il materiale della chiave per la chiave condivisa, vedere [esempio di federazione](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="838e6-160">For more information about how to construct the proof token when the client and the security token service both provide key material for the shared key, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
 <span data-ttu-id="838e6-161">I riferimenti del token rilasciato sono costruiti creando istanze della classe <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>.</span><span class="sxs-lookup"><span data-stu-id="838e6-161">The issued token references are constructed by creating instances of the <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> class.</span></span>  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 <span data-ttu-id="838e6-162">Tutti questi diversi valori vengono quindi serializzati nel messaggio di risposta restituito al client.</span><span class="sxs-lookup"><span data-stu-id="838e6-162">These various values are then serialized into the response message returned to the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="838e6-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="838e6-163">Example</span></span>  
 <span data-ttu-id="838e6-164">Per il codice completo per un servizio token di sicurezza, vedere [esempio di federazione](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="838e6-164">For full code for a security token service, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="838e6-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="838e6-165">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SigningCredentials>  
 <xref:System.IdentityModel.Tokens.SecurityKey>  
 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
 <xref:System.IdentityModel.Tokens.SamlAssertion>  
 <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>  
 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>  
 [<span data-ttu-id="838e6-166">Esempio di federazione</span><span class="sxs-lookup"><span data-stu-id="838e6-166">Federation Sample</span></span>](../../../../docs/framework/wcf/samples/federation-sample.md)
