---
title: Autorizzazione in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 0097adc3d9677d9ce5595a3ac632b51d94d53f6f
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964681"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="935df-102">Autorizzazione in WCF</span><span class="sxs-lookup"><span data-stu-id="935df-102">Authorization in WCF</span></span>
<span data-ttu-id="935df-103">L'autorizzazione è il processo di controllo dell'accesso e dei diritti alle risorse, ad esempio servizi o file.</span><span class="sxs-lookup"><span data-stu-id="935df-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="935df-104">Negli argomenti di questa sezione viene illustrato come eseguire questa attività di base in Windows Communication Foundation (WCF) in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="935df-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="935df-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="935df-105">In This Section</span></span>  
 [<span data-ttu-id="935df-106">Meccanismi del controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="935df-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="935df-107">Viene fornita una breve descrizione dei meccanismi di autorizzazione in WCF e degli utilizzi consigliati.</span><span class="sxs-lookup"><span data-stu-id="935df-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="935df-108">Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="935df-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="935df-109">Viene illustrato il processo di restrizione dell'accesso a un servizio con l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="935df-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="935df-110">Procedura: Usare il provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="935df-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="935df-111">Viene illustrata la configurazione di un servizio per consentire l'uso della funzionalità del provider di ruoli di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="935df-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="935df-112">Procedura: usare il provider di ruoli ASP.NET di Gestione autorizzazioni con un servizio</span><span class="sxs-lookup"><span data-stu-id="935df-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="935df-113">ASP.NET può utilizzare Gestione autorizzazioni per gestire l'autorizzazione per un sito Web.</span><span class="sxs-lookup"><span data-stu-id="935df-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="935df-114">WCF può sfruttare in modo analogo la combinazione di ASP.NET/Authorization Manager per l'autorizzazione dei client.</span><span class="sxs-lookup"><span data-stu-id="935df-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="935df-115">Gestione delle attestazioni e dell'autorizzazione con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="935df-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="935df-116">Vengono spiegate le nozioni di base dell'utilizzo dell'infrastruttura del modello di identità per l'autorizzazione basata su richieste.</span><span class="sxs-lookup"><span data-stu-id="935df-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="935df-117">Delega e rappresentazione</span><span class="sxs-lookup"><span data-stu-id="935df-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="935df-118">Viene spiegata la differenza tra delega e rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="935df-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="935df-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="935df-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="935df-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="935df-120">Related Sections</span></span>  
 [<span data-ttu-id="935df-121">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="935df-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="935df-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="935df-122">See also</span></span>

- [<span data-ttu-id="935df-123">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="935df-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="935df-124">[Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="935df-124">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
