---
title: Autorizzazione in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac43b2185048287d0edd4cb20561a936bce2f58b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="84790-102">Autorizzazione in WCF</span><span class="sxs-lookup"><span data-stu-id="84790-102">Authorization in WCF</span></span>
<span data-ttu-id="84790-103">L'autorizzazione è il processo di controllo dell'accesso e dei diritti alle risorse, ad esempio servizi o file.</span><span class="sxs-lookup"><span data-stu-id="84790-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="84790-104">Negli argomenti di questa sezione viene illustrato come eseguire questa attività di base in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in una serie di modi.</span><span class="sxs-lookup"><span data-stu-id="84790-104">The topics in this section show you how to perform this basic task in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84790-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="84790-105">In This Section</span></span>  
 [<span data-ttu-id="84790-106">Meccanismi del controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="84790-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="84790-107">Viene fornita una breve descrizione dei meccanismi di autorizzazione in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e degli utilizzi consigliati.</span><span class="sxs-lookup"><span data-stu-id="84790-107">Provides a brief outline of the authorization mechanisms in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and suggested uses.</span></span>  
  
 [<span data-ttu-id="84790-108">Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="84790-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="84790-109">Viene illustrato il processo di restrizione dell'accesso a un servizio con l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="84790-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="84790-110">Procedura: Usare il provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="84790-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="84790-111">Viene illustrata la configurazione di un servizio per attivare l'utilizzo della funzionalità del provider di ruoli di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84790-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="84790-112">Procedura: usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio</span><span class="sxs-lookup"><span data-stu-id="84790-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="84790-113">In [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è possibile utilizzare Gestione autorizzazioni per gestire l'autorizzazione di un sito Web.</span><span class="sxs-lookup"><span data-stu-id="84790-113">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="84790-114">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è allo stesso modo possibile sfruttare la combinazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Gestione autorizzazioni per l'autorizzazione di client.</span><span class="sxs-lookup"><span data-stu-id="84790-114">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="84790-115">Gestione delle attestazioni e dell'autorizzazione con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="84790-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="84790-116">Vengono spiegate le nozioni di base dell'utilizzo dell'infrastruttura del modello di identità per l'autorizzazione basata su richieste.</span><span class="sxs-lookup"><span data-stu-id="84790-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="84790-117">Delega e rappresentazione</span><span class="sxs-lookup"><span data-stu-id="84790-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="84790-118">Viene spiegata la differenza tra delega e rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="84790-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="84790-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="84790-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="84790-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="84790-120">Related Sections</span></span>  
 [<span data-ttu-id="84790-121">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="84790-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="84790-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84790-122">See Also</span></span>  
 [<span data-ttu-id="84790-123">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="84790-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="84790-124">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="84790-124">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
