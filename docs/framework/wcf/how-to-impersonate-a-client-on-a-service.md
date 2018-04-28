---
title: 'Procedura: rappresentare un client in un servizio'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 95330e062ff0ab6ba080deeb01a73bb64fac4dfc
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-impersonate-a-client-on-a-service"></a><span data-ttu-id="f9122-102">Procedura: rappresentare un client in un servizio</span><span class="sxs-lookup"><span data-stu-id="f9122-102">How to: Impersonate a Client on a Service</span></span>
<span data-ttu-id="f9122-103">La rappresentazione di un client in un servizio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] consente a quest'ultimo di eseguire azioni per conto del client.</span><span class="sxs-lookup"><span data-stu-id="f9122-103">Impersonating a client on a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service enables the service to perform actions on behalf of the client.</span></span> <span data-ttu-id="f9122-104">Per le azioni soggette ai controlli dell'elenco di controllo di accesso (ACL), ad esempio l'accesso a directory e file in un computer o l'accesso a un database SQL Server, il controllo ACL si basa sull'account utente del client.</span><span class="sxs-lookup"><span data-stu-id="f9122-104">For actions subject to access control list (ACL) checks, such as access to directories and files on a machine or access to a SQL Server database, the ACL check is against the client user account.</span></span> <span data-ttu-id="f9122-105">In questo argomento vengono illustrati i passaggi di base necessari che consentono a un client in un dominio Windows di impostare un livello di rappresentazione di client.</span><span class="sxs-lookup"><span data-stu-id="f9122-105">This topic shows the basic steps required to enable a client in a Windows domain to set a client impersonation level.</span></span> <span data-ttu-id="f9122-106">Per un esempio pratico, vedere [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md).</span><span class="sxs-lookup"><span data-stu-id="f9122-106">For a working example of this, see [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="f9122-107"> la rappresentazione del client, vedere [delega e rappresentazione](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="f9122-107"> client impersonation, see [Delegation and Impersonation](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9122-108">Quando il client e il servizio sono in esecuzione nello stesso computer e il client è in esecuzione con un account del sistema (ad esempio `Local System` o `Network Service`), il client non può essere rappresentato quando viene stabilita una sessione protetta con token del contesto di sicurezza con stato.</span><span class="sxs-lookup"><span data-stu-id="f9122-108">When the client and service are running on the same computer and the client is running under a system account (that is, `Local System` or `Network Service`), the client cannot be impersonated when a secure session is established with stateful Security Context tokens.</span></span> <span data-ttu-id="f9122-109">Un'applicazione Windows Form o console viene in genere eseguita con l'account attualmente connesso che quindi può essere rappresentato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f9122-109">A WinForms or console application typically is run under the currently logged in account, so that account can be impersonated by default.</span></span> <span data-ttu-id="f9122-110">Tuttavia, quando il client è una pagina [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] ospitata in [!INCLUDE[iis601](../../../includes/iis601-md.md)] o IIS 7.0, il client viene eseguito con l'account `Network Service` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f9122-110">However, when the client is an [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] page and that page is hosted in [!INCLUDE[iis601](../../../includes/iis601-md.md)] or IIS 7.0, then the client does run under the `Network Service` account by default.</span></span> <span data-ttu-id="f9122-111">Tutte le associazioni fornite dal sistema che supportano le sessioni protette utilizzano un token del contesto di sicurezza senza stato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f9122-111">All of the system-provided bindings that support secure sessions use a stateless Security Context token by default.</span></span> <span data-ttu-id="f9122-112">Tuttavia, se il client è una pagina [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] e si utilizzano sessioni protette con token del contesto di sicurezza con stato, non è possibile eseguire la rappresentazione del client.</span><span class="sxs-lookup"><span data-stu-id="f9122-112">However, if the client is an [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] page and secure sessions with stateful Security Context tokens are used, the client cannot be impersonated.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="f9122-113"> uso di token del contesto di sicurezza con stato in una sessione protetta, vedere [procedura: creare un Token di contesto di sicurezza per una sessione protetta](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="f9122-113"> using stateful Security Context tokens in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a><span data-ttu-id="f9122-114">Per consentire la rappresentazione di un client da un token di Windows memorizzato nella cache in un servizio</span><span class="sxs-lookup"><span data-stu-id="f9122-114">To enable impersonation of a client from a cached Windows token on a service</span></span>  
  
1.  <span data-ttu-id="f9122-115">Creare il servizio.</span><span class="sxs-lookup"><span data-stu-id="f9122-115">Create the service.</span></span> <span data-ttu-id="f9122-116">Per un'esercitazione su questa procedura di base, vedere [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f9122-116">For a tutorial of this basic procedure, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
2.  <span data-ttu-id="f9122-117">Utilizzare un'associazione che utilizza l'autenticazione di Windows e che crea una sessione, ad esempio <xref:System.ServiceModel.NetTcpBinding> o <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f9122-117">Use a binding that uses Windows authentication and creates a session, such as <xref:System.ServiceModel.NetTcpBinding> or <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
3.  <span data-ttu-id="f9122-118">Quando si crea l'implementazione dell'interfaccia del servizio, applicare la classe <xref:System.ServiceModel.OperationBehaviorAttribute> al metodo che richiede la rappresentazione del client.</span><span class="sxs-lookup"><span data-stu-id="f9122-118">When creating the implementation of the service's interface, apply the <xref:System.ServiceModel.OperationBehaviorAttribute> class to the method that requires client impersonation.</span></span> <span data-ttu-id="f9122-119">Impostare la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> su <xref:System.ServiceModel.ImpersonationOption.Required>.</span><span class="sxs-lookup"><span data-stu-id="f9122-119">Set the <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> property to <xref:System.ServiceModel.ImpersonationOption.Required>.</span></span>  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a><span data-ttu-id="f9122-120">Per impostare il livello di rappresentazione consentito nel client</span><span class="sxs-lookup"><span data-stu-id="f9122-120">To set the allowed impersonation level on the client</span></span>  
  
1.  <span data-ttu-id="f9122-121">Creare un codice client del servizio tramite [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f9122-121">Create service client code by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="f9122-122">Per altre informazioni, vedere [accesso ai servizi tramite Client WCF](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="f9122-122">For more information, see [Accessing Services Using a WCF Client](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="f9122-123">Dopo la creazione del client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , impostare la proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> della classe <xref:System.ServiceModel.Security.WindowsClientCredential> su uno dei valori di enumerazione di <xref:System.Security.Principal.TokenImpersonationLevel> .</span><span class="sxs-lookup"><span data-stu-id="f9122-123">After creating the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, set the <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property of the <xref:System.ServiceModel.Security.WindowsClientCredential> class to one of the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration values.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9122-124">Per usare <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, deve essere usata l'autenticazione Kerberos negoziata, a volte denominata *multifase* o *in più passaggi* .</span><span class="sxs-lookup"><span data-stu-id="f9122-124">To use <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, negotiated Kerberos authentication (sometimes called *multi-leg* or *multi-step* Kerberos) must be used.</span></span> <span data-ttu-id="f9122-125">Per una descrizione di come implementare questo, vedere [le procedure consigliate per la sicurezza](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="f9122-125">For a description of how to implement this, see [Best Practices for Security](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).</span></span>  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f9122-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9122-126">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 [<span data-ttu-id="f9122-127">Rappresentazione del client</span><span class="sxs-lookup"><span data-stu-id="f9122-127">Impersonating the Client</span></span>](../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 [<span data-ttu-id="f9122-128">Delega e rappresentazione</span><span class="sxs-lookup"><span data-stu-id="f9122-128">Delegation and Impersonation</span></span>](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
