---
title: 'Procedura: creare un provider di token di sicurezza personalizzati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 37e7f9541457c475bfe187485520df63a84f7555
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-custom-security-token-provider"></a><span data-ttu-id="b6203-102">Procedura: creare un provider di token di sicurezza personalizzati</span><span class="sxs-lookup"><span data-stu-id="b6203-102">How to: Create a Custom Security Token Provider</span></span>
<span data-ttu-id="b6203-103">In questo argomento viene illustrato come creare nuovi tipi di token con un provider di token di sicurezza personalizzati e come integrare il provider con un gestore di token di sicurezza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b6203-103">This topic shows how to create new token types with a custom security token provider and how to integrate the provider with a custom security token manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6203-104">Creare un provider di token personalizzati se i token forniti dal sistema, presenti nello spazio dei nomi <xref:System.IdentityModel.Tokens>, non corrispondono ai propri requisiti.</span><span class="sxs-lookup"><span data-stu-id="b6203-104">Create a custom token provider if the system-provided tokens found in the <xref:System.IdentityModel.Tokens> namespace do not match your requirements.</span></span>  
  
 <span data-ttu-id="b6203-105">Il provider di token di sicurezza crea una rappresentazione dei token di sicurezza in base alle informazioni presenti nelle credenziali del client o del servizio.</span><span class="sxs-lookup"><span data-stu-id="b6203-105">The security token provider creates a security token representation based on information in the client or service credentials.</span></span> <span data-ttu-id="b6203-106">Per usare il provider di token di sicurezza personalizzati nella protezione [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], è necessario creare credenziali personalizzate e implementazioni del gestore dei token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6203-106">To use the custom security token provider in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security, you must create custom credentials and security token manager implementations.</span></span>  
  
 <span data-ttu-id="b6203-107">Per ulteriori informazioni sulle credenziali personalizzate e gestore del token di sicurezza, vedere il [procedura dettagliata: creazione di Client personalizzato e credenziali del servizio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="b6203-107">For more information about custom credentials and security token manager see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="b6203-108">Per ulteriori informazioni sulle credenziali, token manager, provider e autenticatore classi di protezione, vedere il [architettura di sicurezza](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f).</span><span class="sxs-lookup"><span data-stu-id="b6203-108">For more information about credentials, security token manager, provider and authenticator classes, see the [Security Architecture](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f).</span></span>  
  
### <a name="to-create-a-custom-security-token-provider"></a><span data-ttu-id="b6203-109">Per creare un provider di token di sicurezza personalizzati</span><span class="sxs-lookup"><span data-stu-id="b6203-109">To create a custom security token provider</span></span>  
  
1.  <span data-ttu-id="b6203-110">Definire una nuova classe derivata dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.</span><span class="sxs-lookup"><span data-stu-id="b6203-110">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class.</span></span>  
  
2.  <span data-ttu-id="b6203-111">Implementare il metodo <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>.</span><span class="sxs-lookup"><span data-stu-id="b6203-111">Implement the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="b6203-112">Il metodo è responsabile della creazione e della restituzione di un'istanza del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6203-112">The method is responsible for creating and returning an instance of the security token.</span></span> <span data-ttu-id="b6203-113">Nell'esempio seguente viene creata una classe denominata `MySecurityTokenProvider` ed eseguito l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>, per restituire un'istanza della classe <xref:System.IdentityModel.Tokens.X509SecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="b6203-113">The following example creates a class named `MySecurityTokenProvider`, and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method to return an instance of the <xref:System.IdentityModel.Tokens.X509SecurityToken> class.</span></span> <span data-ttu-id="b6203-114">Il costruttore della classe richiede un'istanza della classe <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.</span><span class="sxs-lookup"><span data-stu-id="b6203-114">The class constructor requires an instance of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class.</span></span>  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a><span data-ttu-id="b6203-115">Per integrare un provider di token di sicurezza personalizzati con un gestore di token di sicurezza personalizzati</span><span class="sxs-lookup"><span data-stu-id="b6203-115">To integrate a custom security token provider with a custom security token manager</span></span>  
  
1.  <span data-ttu-id="b6203-116">Definire una nuova classe derivata dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenManager>.</span><span class="sxs-lookup"><span data-stu-id="b6203-116">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span> <span data-ttu-id="b6203-117">L'esempio seguente deriva dalla classe <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, che deriva dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenManager>.</span><span class="sxs-lookup"><span data-stu-id="b6203-117">(The example below derives from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class, which derives from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.)</span></span>  
  
2.  <span data-ttu-id="b6203-118">Eseguire l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>, se non lo si è già fatto.</span><span class="sxs-lookup"><span data-stu-id="b6203-118">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if is not already overridden.</span></span>  
  
     <span data-ttu-id="b6203-119">Il metodo <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> è responsabile della restituzione di un'istanza della classe <xref:System.IdentityModel.Selectors.SecurityTokenProvider> adatta al parametro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> passato al metodo dal framework di sicurezza [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6203-119">The <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method is responsible for returning an instance of the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class appropriate to the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter passed to the method by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework.</span></span> <span data-ttu-id="b6203-120">Modificare il metodo per restituire l'implementazione del provider di token di sicurezza personalizzati (creato nella procedura precedente), quando il metodo viene chiamato con un parametro del token di sicurezza appropriato.</span><span class="sxs-lookup"><span data-stu-id="b6203-120">Modify the method to return the custom security token provider implementation (created in the previous procedure) when the method is called with an appropriate security token parameter.</span></span> <span data-ttu-id="b6203-121">Per ulteriori informazioni sul gestore di token di sicurezza, vedere il [procedura dettagliata: creazione di Client personalizzato e credenziali del servizio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="b6203-121">For more information about the security token manager, see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
3.  <span data-ttu-id="b6203-122">Aggiungere logica personalizzata al metodo, per consentire la restituzione del provider di token di sicurezza personalizzati in base al parametro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>.</span><span class="sxs-lookup"><span data-stu-id="b6203-122">Add custom logic to the method to enable it to return your custom security token provider based on the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter.</span></span> <span data-ttu-id="b6203-123">Nell'esempio seguente viene restituito il provider di token di sicurezza personalizzati, se i requisiti dei token vengono soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="b6203-123">The following sample returns the custom security token provider if the token requirements are met.</span></span> <span data-ttu-id="b6203-124">I requisiti includono un token di sicurezza X.509 e la direzione dei messaggi (è necessario che il token venga usato per l'output dei messaggi).</span><span class="sxs-lookup"><span data-stu-id="b6203-124">The requirements include an X.509 security token and the message direction (that the token is used for message output).</span></span> <span data-ttu-id="b6203-125">Per tutti gli altri casi, il codice chiama la classe di base per mantenere il comportamento fornito dal sistema per gli altri requisiti dei token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6203-125">For all other cases, the code calls the base class to maintain the system-provided behavior for other security token requirements.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="b6203-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6203-126">Example</span></span>  
 <span data-ttu-id="b6203-127">Nell'esempio seguente viene illustrata un'implementazione completa di <xref:System.IdentityModel.Selectors.SecurityTokenProvider>, insieme a un'implementazione di <xref:System.IdentityModel.Selectors.SecurityTokenManager> corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b6203-127">The following shows a complete <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation along with a corresponding <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementation.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="b6203-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6203-128">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [<span data-ttu-id="b6203-129">Procedura dettagliata: creazione di credenziali client e del servizio personalizzate</span><span class="sxs-lookup"><span data-stu-id="b6203-129">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [<span data-ttu-id="b6203-130">Procedura: Creare un autenticatore del token di sicurezza personalizzato</span><span class="sxs-lookup"><span data-stu-id="b6203-130">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [<span data-ttu-id="b6203-131">Architettura di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b6203-131">Security Architecture</span></span>](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
