---
title: 'Procedura: Creare un verificatore di identità client personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
ms.openlocfilehash: 86e7869efdba50d72cc61a1aebb767cf43927546
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795637"
---
# <a name="how-to-create-a-custom-client-identity-verifier"></a><span data-ttu-id="45ca5-102">Procedura: Creare un verificatore di identità client personalizzato</span><span class="sxs-lookup"><span data-stu-id="45ca5-102">How to: Create a Custom Client Identity Verifier</span></span>
<span data-ttu-id="45ca5-103">La funzionalità di *identità* di Windows Communication Foundation (WCF) consente a un client di specificare in anticipo l'identità prevista del servizio.</span><span class="sxs-lookup"><span data-stu-id="45ca5-103">The *identity* feature of Windows Communication Foundation (WCF) enables a client to specify in advance the expected identity of the service.</span></span> <span data-ttu-id="45ca5-104">Ogni volta che un server esegue l'autenticazione al client, l'identità viene confrontata con l'identità prevista.</span><span class="sxs-lookup"><span data-stu-id="45ca5-104">Whenever a server authenticates itself to the client, the identity is checked against the expected identity.</span></span> <span data-ttu-id="45ca5-105">Per una spiegazione dell'identità e del relativo funzionamento, vedere [identità e autenticazione del servizio](../feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="45ca5-105">(For an explanation of identity and how it works, see [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md).)</span></span>  
  
 <span data-ttu-id="45ca5-106">Se necessario, la verifica può essere personalizzata usando un verificatore di identità personalizzato.</span><span class="sxs-lookup"><span data-stu-id="45ca5-106">If needed, the verification can be customized using a custom identity verifier.</span></span> <span data-ttu-id="45ca5-107">È possibile, ad esempio, eseguire ulteriori controlli di verifica dell'identità del servizio.</span><span class="sxs-lookup"><span data-stu-id="45ca5-107">For example, you can perform additional service identity verification checks.</span></span> <span data-ttu-id="45ca5-108">In questo esempio il verificatore di identità personalizzato verifica le attestazioni aggiuntive nel certificato X.509 restituito dal server.</span><span class="sxs-lookup"><span data-stu-id="45ca5-108">In this example, the custom identity verifier checks additional claims in the X.509 certificate returned from the server.</span></span> <span data-ttu-id="45ca5-109">Per un'applicazione di esempio, vedere [esempio di identità del servizio](../samples/service-identity-sample.md).</span><span class="sxs-lookup"><span data-stu-id="45ca5-109">For a sample application, see [Service Identity Sample](../samples/service-identity-sample.md).</span></span>  
  
### <a name="to-extend-the-endpointidentity-class"></a><span data-ttu-id="45ca5-110">Per estendere la classe EndpointIdentity</span><span class="sxs-lookup"><span data-stu-id="45ca5-110">To extend the EndpointIdentity class</span></span>  
  
1. <span data-ttu-id="45ca5-111">Definire una nuova classe che deriva dalla classe <xref:System.ServiceModel.EndpointIdentity>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-111">Define a new class that derives from the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="45ca5-112">Questo esempio attribuisce un nome all'estensione `OrgEndpointIdentity`.</span><span class="sxs-lookup"><span data-stu-id="45ca5-112">This example names the extension `OrgEndpointIdentity`.</span></span>  
  
2. <span data-ttu-id="45ca5-113">Aggiungere membri privati insieme a proprietà che verranno usate dalla classe <xref:System.ServiceModel.Security.IdentityVerifier> estesa per eseguire il controllo dell'identità rispetto alle attestazioni incluse nel token di sicurezza restituito dal servizio.</span><span class="sxs-lookup"><span data-stu-id="45ca5-113">Add private members along with properties that will be used by the extended <xref:System.ServiceModel.Security.IdentityVerifier> class to perform the identity check against claims in the security token returned from the service.</span></span> <span data-ttu-id="45ca5-114">Questo esempio definisce una proprietà, ovvero `OrganizationClaim`.</span><span class="sxs-lookup"><span data-stu-id="45ca5-114">This example defines one property: the `OrganizationClaim` property.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### <a name="to-extend-the-identityverifier-class"></a><span data-ttu-id="45ca5-115">Per estendere la classe IdentityVerifier</span><span class="sxs-lookup"><span data-stu-id="45ca5-115">To extend the IdentityVerifier class</span></span>  
  
1. <span data-ttu-id="45ca5-116">Definire una nuova classe che deriva dall'interfaccia <xref:System.ServiceModel.Security.IdentityVerifier>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-116">Define a new class that derives from <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="45ca5-117">Questo esempio attribuisce un nome all'estensione `CustomIdentityVerifier`.</span><span class="sxs-lookup"><span data-stu-id="45ca5-117">This example names the extension `CustomIdentityVerifier`.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2. <span data-ttu-id="45ca5-118">Eseguire l'override del metodo <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> .</span><span class="sxs-lookup"><span data-stu-id="45ca5-118">Override the <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> method.</span></span> <span data-ttu-id="45ca5-119">Il metodo determina se il controllo dell'identità ha esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="45ca5-119">The method determines whether the identity check succeeded or failed.</span></span>  
  
3. <span data-ttu-id="45ca5-120">Il metodo `CheckAccess` ha due parametri.</span><span class="sxs-lookup"><span data-stu-id="45ca5-120">The `CheckAccess` method has two parameters.</span></span> <span data-ttu-id="45ca5-121">Il primo è un'istanza della classe <xref:System.ServiceModel.EndpointIdentity>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-121">The first is an instance of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="45ca5-122">Il secondo è un'istanza della classe <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-122">The second is an instance of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
     <span data-ttu-id="45ca5-123">Nell'implementazione del metodo, esaminare la raccolta di attestazioni restituita dalla proprietà <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> della classe <xref:System.IdentityModel.Policy.AuthorizationContext> ed eseguire i controlli di autenticazione necessari.</span><span class="sxs-lookup"><span data-stu-id="45ca5-123">In the method implementation, examine the collection of claims returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class, and perform authentication checks as required.</span></span> <span data-ttu-id="45ca5-124">Questo esempio inizia cercando qualsiasi attestazione di tipo "Nome distinto" e confronta quindi il nome all'estensione della classe <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span><span class="sxs-lookup"><span data-stu-id="45ca5-124">This example begins by finding any claim that is of type "Distinguished Name" and then compares the name to the extension of the <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### <a name="to-implement-the-trygetidentity-method"></a><span data-ttu-id="45ca5-125">Per implementare il metodo TryGetIdentity</span><span class="sxs-lookup"><span data-stu-id="45ca5-125">To implement the TryGetIdentity method</span></span>  
  
1. <span data-ttu-id="45ca5-126">Implementare il metodo <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> che determina se un'istanza della classe <xref:System.ServiceModel.EndpointIdentity> può essere restituita dal client.</span><span class="sxs-lookup"><span data-stu-id="45ca5-126">Implement the <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> method, which determines whether an instance of the <xref:System.ServiceModel.EndpointIdentity> class can be returned by the client.</span></span> <span data-ttu-id="45ca5-127">L'infrastruttura WCF chiama prima l'implementazione del `TryGetIdentity` metodo per recuperare l'identità del servizio dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="45ca5-127">The WCF infrastructure calls the implementation of the `TryGetIdentity` method first to retrieve the service's identity from the message.</span></span> <span data-ttu-id="45ca5-128">L'infrastruttura chiama quindi l'implementazione `CheckAccess` con le classi `EndpointIdentity` e <xref:System.IdentityModel.Policy.AuthorizationContext> restituite.</span><span class="sxs-lookup"><span data-stu-id="45ca5-128">Next, the infrastructure calls the `CheckAccess` implementation with the returned `EndpointIdentity` and <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span>  
  
2. <span data-ttu-id="45ca5-129">Nel metodo `TryGetIdentity` inserire il seguente codice:</span><span class="sxs-lookup"><span data-stu-id="45ca5-129">In the `TryGetIdentity` method, put the following code:</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### <a name="to-implement-a-custom-binding-and-set-the-custom-identityverifier"></a><span data-ttu-id="45ca5-130">Per implementare un'associazione personalizzata e impostare il verificatore di identità personalizzato</span><span class="sxs-lookup"><span data-stu-id="45ca5-130">To implement a custom binding and set the custom IdentityVerifier</span></span>  
  
1. <span data-ttu-id="45ca5-131">Creare un metodo che restituisca un oggetto <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-131">Create a method that returns a <xref:System.ServiceModel.Channels.Binding> object.</span></span> <span data-ttu-id="45ca5-132">Questo esempio inizia con la creazione di un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e imposta la propria modalità di sicurezza su <xref:System.ServiceModel.SecurityMode.Message>e la propria proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> su <xref:System.ServiceModel.MessageCredentialType.None>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-132">This example begins creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class and sets its security mode to <xref:System.ServiceModel.SecurityMode.Message>, and its <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> to <xref:System.ServiceModel.MessageCredentialType.None>.</span></span>  
  
2. <span data-ttu-id="45ca5-133">Creare una classe <xref:System.ServiceModel.Channels.BindingElementCollection> usando il metodo <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-133">Create a <xref:System.ServiceModel.Channels.BindingElementCollection> using the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="45ca5-134">Restituire la classe <xref:System.ServiceModel.Channels.SecurityBindingElement> dalla raccolta ed eseguirne il cast su una variabile <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-134">Return the <xref:System.ServiceModel.Channels.SecurityBindingElement> from the collection and cast it to a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> variable.</span></span>  
  
4. <span data-ttu-id="45ca5-135">Imposta la proprietà <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> della classe <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> su una nuova istanza della classe `CustomIdentityVerifier` creata precedentemente.</span><span class="sxs-lookup"><span data-stu-id="45ca5-135">Set the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> property of the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class to a new instance of the `CustomIdentityVerifier` class created previously.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5. <span data-ttu-id="45ca5-136">L'associazione personalizzata restituita viene usata per creare un'istanza del client e della classe.</span><span class="sxs-lookup"><span data-stu-id="45ca5-136">The custom binding that is returned is used to create an instance of the client and class.</span></span> <span data-ttu-id="45ca5-137">Il client può eseguire quindi un controllo di verifica dell'identità del servizio personalizzato, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="45ca5-137">The client can then perform a custom identity verification check of the service as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="45ca5-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="45ca5-138">Example</span></span>  
 <span data-ttu-id="45ca5-139">Nell'esempio seguente viene illustrata un'implementazione completa della classe <xref:System.ServiceModel.Security.IdentityVerifier>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-139">The following example shows a complete implementation of the <xref:System.ServiceModel.Security.IdentityVerifier> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="45ca5-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="45ca5-140">Example</span></span>  
 <span data-ttu-id="45ca5-141">Nell'esempio seguente viene illustrata un'implementazione completa della classe <xref:System.ServiceModel.EndpointIdentity>.</span><span class="sxs-lookup"><span data-stu-id="45ca5-141">The following example shows a complete implementation of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="45ca5-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45ca5-142">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- <xref:System.ServiceModel.EndpointIdentity>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [<span data-ttu-id="45ca5-143">Esempio identità del servizio</span><span class="sxs-lookup"><span data-stu-id="45ca5-143">Service Identity Sample</span></span>](../samples/service-identity-sample.md)
- [<span data-ttu-id="45ca5-144">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="45ca5-144">Authorization Policy</span></span>](../samples/authorization-policy.md)
