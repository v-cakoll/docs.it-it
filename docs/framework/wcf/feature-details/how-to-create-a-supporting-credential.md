---
title: 'Procedura: creare una credenziale di supporto'
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: 3f33bf5a78c575237ee4bc609a482a81fd30fc53
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964554"
---
# <a name="how-to-create-a-supporting-credential"></a><span data-ttu-id="1896e-102">Procedura: creare una credenziale di supporto</span><span class="sxs-lookup"><span data-stu-id="1896e-102">How to: Create a Supporting Credential</span></span>
<span data-ttu-id="1896e-103">È possibile avere uno schema di sicurezza personalizzato che richiede più di una credenziale.</span><span class="sxs-lookup"><span data-stu-id="1896e-103">It is possible to have a custom security scheme that requires more than one credential.</span></span> <span data-ttu-id="1896e-104">Ad esempio, è possibile che un servizio richieda a un client non solo un nome utente e una password, ma anche una credenziale che dimostri che l'utente del client abbia un'età superiore a 18 anni.</span><span class="sxs-lookup"><span data-stu-id="1896e-104">For example, a service may demand from the client not just a user name and password, but also a credential that proves the client is over the age of 18.</span></span> <span data-ttu-id="1896e-105">La seconda credenziale è una *credenziale di supporto*.</span><span class="sxs-lookup"><span data-stu-id="1896e-105">The second credential is a *supporting credential*.</span></span> <span data-ttu-id="1896e-106">In questo argomento viene illustrato come implementare tali credenziali in un client Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1896e-106">This topic explains how to implement such credentials in an Windows Communication Foundation (WCF) client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1896e-107">La specifica per supportare le credenziali è parte della specifica SecurityPolicy-WS.</span><span class="sxs-lookup"><span data-stu-id="1896e-107">The specification for supporting credentials is part of the WS-SecurityPolicy specification.</span></span> <span data-ttu-id="1896e-108">Per ulteriori informazioni, vedere la pagina relativa alle [specifiche Web Services Security](https://docs.microsoft.com/previous-versions/dotnet/articles/ms951273(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="1896e-108">For more information, see [Web Services Security Specifications](https://docs.microsoft.com/previous-versions/dotnet/articles/ms951273(v=msdn.10)).</span></span>  
  
## <a name="supporting-tokens"></a><span data-ttu-id="1896e-109">Token di supporto</span><span class="sxs-lookup"><span data-stu-id="1896e-109">Supporting Tokens</span></span>  
 <span data-ttu-id="1896e-110">In breve, quando si utilizza la sicurezza dei messaggi, viene sempre utilizzata una *credenziale primaria* per proteggere il messaggio (ad esempio, un certificato X. 509 o un ticket Kerberos).</span><span class="sxs-lookup"><span data-stu-id="1896e-110">In brief, when you use message security, a *primary credential* is always used to secure the message (for example, an X.509 certificate or a Kerberos ticket).</span></span>  
  
 <span data-ttu-id="1896e-111">Come definito dalla specifica, un'associazione di sicurezza utilizza i *token* per proteggere lo scambio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="1896e-111">As defined by the specification, a security binding uses *tokens* to secure the message exchange.</span></span> <span data-ttu-id="1896e-112">Un *token* è una rappresentazione di una credenziale di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1896e-112">A *token* is a representation of a security credential.</span></span>  
  
 <span data-ttu-id="1896e-113">L'associazione di sicurezza usa un token primario identificato nei criteri dell'associazione di sicurezza per creare una firma.</span><span class="sxs-lookup"><span data-stu-id="1896e-113">The security binding uses a primary token identified in the security binding policy to create a signature.</span></span> <span data-ttu-id="1896e-114">Questa firma viene definita *firma del messaggio*.</span><span class="sxs-lookup"><span data-stu-id="1896e-114">This signature is referred to as the *message signature*.</span></span>  
  
 <span data-ttu-id="1896e-115">È possibile specificare token aggiuntivi per aumentare le attestazioni fornite dal token associato alla firma del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1896e-115">Additional tokens can be specified to augment the claims provided by the token associated with the message signature.</span></span>  
  
## <a name="endorsing-signing-and-encrypting"></a><span data-ttu-id="1896e-116">Verifica dell'autenticità, firma e crittografia</span><span class="sxs-lookup"><span data-stu-id="1896e-116">Endorsing, Signing, and Encrypting</span></span>  
 <span data-ttu-id="1896e-117">Una credenziale di supporto produce un *token di supporto* trasmesso all'interno del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1896e-117">A supporting credential results in a *supporting token* transmitted inside the message.</span></span> <span data-ttu-id="1896e-118">La specifica WS-SecurityPolicy definisce quattro modalità per allegare un token di supporto al messaggio, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1896e-118">The WS-SecurityPolicy specification defines four ways to attach a supporting token to the message, as described in the following table.</span></span>  
  
|<span data-ttu-id="1896e-119">Scopo</span><span class="sxs-lookup"><span data-stu-id="1896e-119">Purpose</span></span>|<span data-ttu-id="1896e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1896e-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1896e-121">Firmato</span><span class="sxs-lookup"><span data-stu-id="1896e-121">Signed</span></span>|<span data-ttu-id="1896e-122">Il token di supporto viene incluso nell'intestazione di sicurezza e viene firmato con la firma del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1896e-122">The supporting token is included in the security header and is signed by the message signature.</span></span>|  
|<span data-ttu-id="1896e-123">Verifica dell'autenticità</span><span class="sxs-lookup"><span data-stu-id="1896e-123">Endorsing</span></span>|<span data-ttu-id="1896e-124">Un *token di approvazione* firma la firma del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1896e-124">An *endorsing token* signs the message signature.</span></span>|  
|<span data-ttu-id="1896e-125">Firmato e di verifica dell'autenticità</span><span class="sxs-lookup"><span data-stu-id="1896e-125">Signed and Endorsing</span></span>|<span data-ttu-id="1896e-126">I token di verifica dell'autenticità firmati firmano l'intero elemento `ds:Signature` prodotto dalla firma del messaggio e sono essi stessi firmati con la firma del messaggio; ovvero, entrambi i token, quello usato per la firma del messaggio e quello di verifica dell'autenticità firmato, si firmano l'un l'altro.</span><span class="sxs-lookup"><span data-stu-id="1896e-126">Signed, endorsing tokens sign the entire `ds:Signature` element produced from the message signature and are themselves signed by that message signature; that is, both tokens (the token used for the message signature and the signed endorsing token) sign each other.</span></span>|  
|<span data-ttu-id="1896e-127">Firmato e di crittografia</span><span class="sxs-lookup"><span data-stu-id="1896e-127">Signed and Encrypting</span></span>|<span data-ttu-id="1896e-128">I token di supporto crittografati firmati sono token di supporto firmati che vengono anche crittografati quando sono presenti in `wsse:SecurityHeader`.</span><span class="sxs-lookup"><span data-stu-id="1896e-128">Signed, encrypted supporting tokens are signed supporting tokens that are also encrypted when they appear in the `wsse:SecurityHeader`.</span></span>|  
  
## <a name="programming-supporting-credentials"></a><span data-ttu-id="1896e-129">Programmazione di credenziali di supporto</span><span class="sxs-lookup"><span data-stu-id="1896e-129">Programming Supporting Credentials</span></span>  
 <span data-ttu-id="1896e-130">Per creare un servizio che usa token di supporto, è necessario creare un [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="1896e-130">To create a service that uses supporting tokens you must create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span> <span data-ttu-id="1896e-131">Per altre informazioni, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="1896e-131">(For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span></span>  
  
 <span data-ttu-id="1896e-132">Quando si crea un'associazione personalizzata, il primo passaggio consiste nel creare un elemento di associazione di sicurezza che può essere di uno dei tre tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1896e-132">The first step when creating a custom binding is to create a security binding element, which can be one of three types:</span></span>  
  
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="1896e-133">Tutte le classi ereditano da <xref:System.ServiceModel.Channels.SecurityBindingElement>, che include quattro proprietà rilevanti:</span><span class="sxs-lookup"><span data-stu-id="1896e-133">All classes inherit from the <xref:System.ServiceModel.Channels.SecurityBindingElement>, which includes four relevant properties:</span></span>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a><span data-ttu-id="1896e-134">Ambiti</span><span class="sxs-lookup"><span data-stu-id="1896e-134">Scopes</span></span>  
 <span data-ttu-id="1896e-135">Esistono due ambiti per le credenziali di supporto:</span><span class="sxs-lookup"><span data-stu-id="1896e-135">Two scopes exist for supporting credentials:</span></span>  
  
- <span data-ttu-id="1896e-136">I *token di supporto dell'endpoint* supportano tutte le operazioni di un endpoint.</span><span class="sxs-lookup"><span data-stu-id="1896e-136">*Endpoint supporting tokens* support all operations of an endpoint.</span></span> <span data-ttu-id="1896e-137">In altre parole, la credenziale rappresentata dal token di supporto può essere usata ogni volta che vengono richiamate le operazioni di un endpoint.</span><span class="sxs-lookup"><span data-stu-id="1896e-137">That is, the credential that the supporting token represents can be used whenever any endpoint operations are invoked.</span></span>  
  
- <span data-ttu-id="1896e-138">I *token di supporto dell'operazione* supportano solo una specifica operazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1896e-138">*Operation supporting tokens* support only a specific endpoint operation.</span></span>  
  
 <span data-ttu-id="1896e-139">Come indicato dai nomi delle proprietà, le credenziali di supporto possono essere obbligatorie o facoltative.</span><span class="sxs-lookup"><span data-stu-id="1896e-139">As indicated by the property names, supporting credentials can be either required or optional.</span></span> <span data-ttu-id="1896e-140">In altre parole, se la credenziale di supporto viene usata se presente, anche se non necessaria, l'autenticazione non avrà esito negativo se la credenziale non è presente.</span><span class="sxs-lookup"><span data-stu-id="1896e-140">That is, if the supporting credential is used if it is present, although it is not necessary, but the authentication will not fail if it is not present.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="1896e-141">Procedure</span><span class="sxs-lookup"><span data-stu-id="1896e-141">Procedures</span></span>  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a><span data-ttu-id="1896e-142">Per creare un'associazione personalizzata che includa credenziali di supporto</span><span class="sxs-lookup"><span data-stu-id="1896e-142">To create a custom binding that includes supporting credentials</span></span>  
  
1. <span data-ttu-id="1896e-143">Creare un elemento di associazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1896e-143">Create a security binding element.</span></span> <span data-ttu-id="1896e-144">Nell'esempio seguente viene creata una classe <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> con la modalità di autenticazione `UserNameForCertificate`.</span><span class="sxs-lookup"><span data-stu-id="1896e-144">The example below creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> with the `UserNameForCertificate` authentication mode.</span></span> <span data-ttu-id="1896e-145">Usare il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="1896e-145">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> method.</span></span>  
  
2. <span data-ttu-id="1896e-146">Aggiungere il parametro di supporto alla raccolta dei tipi restituita dalla proprietà appropriata (`Endorsing`, `Signed`, `SignedEncrypted` o `SignedEndorsed`).</span><span class="sxs-lookup"><span data-stu-id="1896e-146">Add the supporting parameter to the collection of types returned by the appropriate property (`Endorsing`, `Signed`, `SignedEncrypted`, or `SignedEndorsed`).</span></span> <span data-ttu-id="1896e-147">I tipi nello spazio dei nomi <xref:System.ServiceModel.Security.Tokens> includono tipi comunemente usati, ad esempio <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="1896e-147">The types in the <xref:System.ServiceModel.Security.Tokens> namespace include commonly used types, such as the <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1896e-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="1896e-148">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1896e-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1896e-149">Description</span></span>  
 <span data-ttu-id="1896e-150">Nell'esempio seguente viene creata un'istanza della classe <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e viene aggiunta un'istanza della classe <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> alla raccolta della proprietà Endorsing restituita.</span><span class="sxs-lookup"><span data-stu-id="1896e-150">The following example creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and adds an instance of the <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> class to the collection the Endorsing property returned.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1896e-151">Codice</span><span class="sxs-lookup"><span data-stu-id="1896e-151">Code</span></span>  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1896e-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1896e-152">See also</span></span>

- [<span data-ttu-id="1896e-153">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1896e-153">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
