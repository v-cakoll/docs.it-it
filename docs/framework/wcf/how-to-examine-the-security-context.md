---
title: 'Procedura: esaminare il contesto di sicurezza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
ms.openlocfilehash: 328d47a583a4f047fd54589a82d339de2cb1a16f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320995"
---
# <a name="how-to-examine-the-security-context"></a><span data-ttu-id="f0c27-102">Procedura: esaminare il contesto di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f0c27-102">How to: Examine the Security Context</span></span>
<span data-ttu-id="f0c27-103">Quando si programmano i servizi di Windows Communication Foundation (WCF), il contesto di sicurezza del servizio consente di determinare i dettagli sulle credenziali client e sulle attestazioni usate per l'autenticazione con il servizio.</span><span class="sxs-lookup"><span data-stu-id="f0c27-103">When programming Windows Communication Foundation (WCF) services, the service security context enables you to determine details about the client credentials and claims used to authenticate with the service.</span></span> <span data-ttu-id="f0c27-104">A tale fine, utilizzare le proprietà della classe <xref:System.ServiceModel.ServiceSecurityContext>.</span><span class="sxs-lookup"><span data-stu-id="f0c27-104">This is done by using the properties of the <xref:System.ServiceModel.ServiceSecurityContext> class.</span></span>  
  
 <span data-ttu-id="f0c27-105">È ad esempio possibile recuperare l'identità del client corrente utilizzando <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> o la proprietà <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0c27-105">For example, you can retrieve the identity of the current client by using the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> or the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property.</span></span> <span data-ttu-id="f0c27-106">Per determinare se il client è anonimo, utilizzare la proprietà <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0c27-106">To determine whether the client is anonymous, use the <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> property.</span></span>  
  
 <span data-ttu-id="f0c27-107">È inoltre possibile determinare quali sono le attestazioni eseguite per conto del client eseguendo un'iterazione nella raccolta di attestazioni nella proprietà <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0c27-107">You can also determine what claims are being made on behalf of the client by iterating through the collection of claims in the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
### <a name="to-get-the-current-security-context"></a><span data-ttu-id="f0c27-108">Per ottenere il contesto di sicurezza corrente</span><span class="sxs-lookup"><span data-stu-id="f0c27-108">To get the current security context</span></span>  
  
- <span data-ttu-id="f0c27-109">Accedere alla proprietà <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> statica per ottenere il contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="f0c27-109">Access the static property <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> to get the current security context.</span></span> <span data-ttu-id="f0c27-110">Esaminare qualsiasi proprietà del contesto corrente dal riferimento.</span><span class="sxs-lookup"><span data-stu-id="f0c27-110">Examine any of the properties of the current context from the reference.</span></span>  
  
### <a name="to-determine-the-identity-of-the-caller"></a><span data-ttu-id="f0c27-111">Per determinare l'identità del chiamante</span><span class="sxs-lookup"><span data-stu-id="f0c27-111">To determine the identity of the caller</span></span>  
  
1. <span data-ttu-id="f0c27-112">Stampare il valore delle proprietà <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> e <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0c27-112">Print the value of the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> properties.</span></span>  
  
### <a name="to-parse-the-claims-of-a-caller"></a><span data-ttu-id="f0c27-113">Per analizzare le attestazioni di un chiamante</span><span class="sxs-lookup"><span data-stu-id="f0c27-113">To parse the claims of a caller</span></span>  
  
1. <span data-ttu-id="f0c27-114">Restituire la classe <xref:System.IdentityModel.Policy.AuthorizationContext> corrente.</span><span class="sxs-lookup"><span data-stu-id="f0c27-114">Return the current <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span> <span data-ttu-id="f0c27-115">Utilizzare la proprietà <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> per restituire il contesto di sicurezza del servizio corrente, quindi restituire `AuthorizationContext` utilizzando la proprietà <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0c27-115">Use the <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> property to return the current service security context, then return the `AuthorizationContext` using the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
2. <span data-ttu-id="f0c27-116">Analizzare la raccolta di oggetti <xref:System.IdentityModel.Claims.ClaimSet> restituiti dalla proprietà <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> della classe <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="f0c27-116">Parse the collection of <xref:System.IdentityModel.Claims.ClaimSet> objects returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0c27-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0c27-117">Example</span></span>  
 <span data-ttu-id="f0c27-118">Nell'esempio seguente vengono stampati i valori delle proprietà <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> e <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> del contesto di sicurezza corrente e la proprietà <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>, il valore della risorsa dell'attestazione e la proprietà <xref:System.IdentityModel.Claims.Claim.Right%2A> di ogni attestazione nel contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="f0c27-118">The following example prints the values of the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> properties of the current security context and the <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> property, the resource value of the claim, and the <xref:System.IdentityModel.Claims.Claim.Right%2A> property of every claim in the current security context.</span></span>  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f0c27-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f0c27-119">Compiling the Code</span></span>  
 <span data-ttu-id="f0c27-120">Il codice utilizza gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0c27-120">The code uses the following namespaces:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.IdentityModel.Policy>  
  
- <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a><span data-ttu-id="f0c27-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0c27-121">See also</span></span>

- [<span data-ttu-id="f0c27-122">Protezione dei servizi</span><span class="sxs-lookup"><span data-stu-id="f0c27-122">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="f0c27-123">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="f0c27-123">Service Identity and Authentication</span></span>](./feature-details/service-identity-and-authentication.md)
