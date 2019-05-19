---
title: Autorizzazione in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 8c605b310f19a05f994296d8f4268b91b408fb18
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881199"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="89466-102">Autorizzazione in WCF</span><span class="sxs-lookup"><span data-stu-id="89466-102">Authorization in WCF</span></span>
<span data-ttu-id="89466-103">L'autorizzazione è il processo di controllo dell'accesso e dei diritti alle risorse, ad esempio servizi o file.</span><span class="sxs-lookup"><span data-stu-id="89466-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="89466-104">Gli argomenti in questa sezione illustrano come eseguire questa attività di base in Windows Communication Foundation (WCF) in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="89466-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89466-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="89466-105">In This Section</span></span>  
 [<span data-ttu-id="89466-106">Meccanismi del controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="89466-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="89466-107">Fornisce una breve descrizione dei meccanismi di autorizzazione in WCF e Usa suggerita.</span><span class="sxs-lookup"><span data-stu-id="89466-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="89466-108">Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="89466-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="89466-109">Viene illustrato il processo di restrizione dell'accesso a un servizio con l'attributo <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="89466-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="89466-110">Procedura: Usare il Provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="89466-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="89466-111">Illustra in dettaglio la configurazione di un servizio per poter usare la funzionalità di provider di ruoli di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="89466-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="89466-112">Procedura: Usare il Provider di ruoli ASP.NET di gestione autorizzazioni con un servizio</span><span class="sxs-lookup"><span data-stu-id="89466-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="89466-113">ASP.NET è possibile utilizzare il gestore dell'autorizzazione per gestire le autorizzazioni per un sito Web.</span><span class="sxs-lookup"><span data-stu-id="89466-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="89466-114">WCF allo stesso modo possibile sfruttare la combinazione di ASP.NET/Authorization Manager per l'autorizzazione dei client.</span><span class="sxs-lookup"><span data-stu-id="89466-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="89466-115">Gestione delle attestazioni e dell'autorizzazione con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="89466-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="89466-116">Vengono spiegate le nozioni di base dell'utilizzo dell'infrastruttura del modello di identità per l'autorizzazione basata su richieste.</span><span class="sxs-lookup"><span data-stu-id="89466-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="89466-117">Delega e rappresentazione</span><span class="sxs-lookup"><span data-stu-id="89466-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="89466-118">Viene spiegata la differenza tra delega e rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="89466-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="89466-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="89466-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="89466-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="89466-120">Related Sections</span></span>  
 [<span data-ttu-id="89466-121">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="89466-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="89466-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89466-122">See also</span></span>

- [<span data-ttu-id="89466-123">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="89466-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="89466-124">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="89466-124">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
