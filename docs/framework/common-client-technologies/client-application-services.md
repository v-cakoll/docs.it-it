---
title: Servizi applicazioni client
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- role-based security [.NET Framework], client application services
- client application services
- credentials [.NET Framework]
- Windows-based applications, client application services
- application settings, client application services
- profiles [ASP.NET], client application services
- logins [client application services]
- sharing information and functionality [client application services]
- Web settings [client application services]
- authentication [ASP.NET], client application services
- ASP.NET services, client application services
- client applications, ASP.NET services
- roles [.NET Framework], client application services
- client application services, about client application services
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 597b2d4d37d76ca722ddcebf9fcfeae532f67a00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="client-application-services"></a><span data-ttu-id="50525-102">Servizi applicazioni client</span><span class="sxs-lookup"><span data-stu-id="50525-102">Client Application Services</span></span>
<span data-ttu-id="50525-103">I servizi delle applicazioni client semplificano la creazione di applicazioni basate su Windows che usano servizi dell'applicazione di accesso, ruoli e profilo di [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] inclusi in Microsoft ASP.NET 2.0 AJAX Extensions.</span><span class="sxs-lookup"><span data-stu-id="50525-103">Client application services make it easy for you to create Windows-based applications that use the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] login, roles, and profile application services included in the Microsoft ASP.NET 2.0 AJAX Extensions.</span></span> <span data-ttu-id="50525-104">Questi servizi consentono a più applicazioni Web e applicazioni basate su Windows di condividere informazioni utente e funzionalità di gestione degli utenti da un singolo server.</span><span class="sxs-lookup"><span data-stu-id="50525-104">These services enable multiple Web and Windows-based applications to share user information and user-management functionality from a single server.</span></span> <span data-ttu-id="50525-105">Ad esempio, è possibile usare questi servizi per eseguire le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="50525-105">For example, you can use these services to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="50525-106">Autenticare un utente.</span><span class="sxs-lookup"><span data-stu-id="50525-106">Authenticate a user.</span></span> <span data-ttu-id="50525-107">È possibile usare il servizio di autenticazione per verificare l'identità di un utente.</span><span class="sxs-lookup"><span data-stu-id="50525-107">You can use the authentication service to verify a user's identity.</span></span>  
  
-   <span data-ttu-id="50525-108">Determinare uno o più ruoli di un utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="50525-108">Determine the role or roles of an authenticated user.</span></span> <span data-ttu-id="50525-109">È possibile usare il servizio ruoli per modificare l'interfaccia utente dell'applicazione in base al ruolo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="50525-109">You can use the roles service to change the user interface of your application depending on the user's role.</span></span> <span data-ttu-id="50525-110">Ad esempio, è possibile fornire funzionalità aggiuntive per gli utenti a cui è assegnato un ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="50525-110">For example, you can provide additional features for users who are in an administrator role.</span></span>  
  
-   <span data-ttu-id="50525-111">Archiviare le impostazioni delle applicazioni per singolo utente presenti nel server e accedervi.</span><span class="sxs-lookup"><span data-stu-id="50525-111">Store and access per-user application settings located on the server.</span></span> <span data-ttu-id="50525-112">È possibile usare il servizio impostazioni Web (noto anche come servizio profilo) per condividere le impostazioni tra più applicazioni e percorsi.</span><span class="sxs-lookup"><span data-stu-id="50525-112">You can use the Web settings service (also known as the profile service) to share settings across multiple applications and locations.</span></span>  
  
 <span data-ttu-id="50525-113">I servizi delle applicazioni client sfruttano il modello di estendibilità dei servizi Web tramite provider di servizi client che è possibile specificare nei file di configurazione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="50525-113">Client application services take advantage of the Web services extensibility model through client service providers that you can specify in your application configuration files.</span></span> <span data-ttu-id="50525-114">Questi provider di servizi includono funzionalità offline che usano una cache locale per i dati relativi all'autenticazione, ai ruoli e alle impostazioni quando non è disponibile una connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="50525-114">These service providers include offline functionality that uses a local cache for authentication, roles, and settings data when a network connection is unavailable.</span></span>  
  
 <span data-ttu-id="50525-115">Per altre informazioni sui servizi delle applicazioni di [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)], vedere [Cenni preliminari sui servizi delle applicazioni ASP.NET](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).</span><span class="sxs-lookup"><span data-stu-id="50525-115">For more information about the [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] application services, see [ASP.NET Application Services Overview](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50525-116">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="50525-116">In This Section</span></span>  
 [<span data-ttu-id="50525-117">Cenni preliminari sui servizi delle applicazioni client</span><span class="sxs-lookup"><span data-stu-id="50525-117">Client Application Services Overview</span></span>](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 <span data-ttu-id="50525-118">Vengono descritte le funzionalità disponibili tramite il provider di servizi delle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="50525-118">Describes the features available through the client application service providers.</span></span>  
  
 [<span data-ttu-id="50525-119">Procedura: Configurare i servizi delle applicazioni client</span><span class="sxs-lookup"><span data-stu-id="50525-119">How to: Configure Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 <span data-ttu-id="50525-120">Viene descritto come usare Creazione progetti di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] per abilitare e configurare i servizi delle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="50525-120">Describes how to use the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project designer to enable and configuration application services.</span></span> <span data-ttu-id="50525-121">Vengono inoltre illustrate le modifiche corrispondenti apportate al file App.config.</span><span class="sxs-lookup"><span data-stu-id="50525-121">Also describes the corresponding changes to your App.config file.</span></span>  
  
 [<span data-ttu-id="50525-122">Procedura: implementare l'accesso utente con i servizi dell'applicazione client</span><span class="sxs-lookup"><span data-stu-id="50525-122">How to: Implement User Login with Client Application Services</span></span>](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 <span data-ttu-id="50525-123">Viene descritto come convalidare un utente quando l'applicazione è configurata per l'uso di un provider di servizi di autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="50525-123">Describes how to validate a user when your application is configured to use a client authentication service provider.</span></span>  
  
 [<span data-ttu-id="50525-124">Procedura dettagliata: uso di servizi delle applicazioni client</span><span class="sxs-lookup"><span data-stu-id="50525-124">Walkthrough: Using Client Application Services</span></span>](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 <span data-ttu-id="50525-125">Viene descritto come combinare tutte le funzionalità dei servizi delle applicazioni client in una singola applicazione.</span><span class="sxs-lookup"><span data-stu-id="50525-125">Describes how to combine all client application services features in a single application.</span></span> <span data-ttu-id="50525-126">Questa procedura dettagliata contiene indicazioni end-to-end,</span><span class="sxs-lookup"><span data-stu-id="50525-126">This walkthrough provides end-to-end guidance.</span></span> <span data-ttu-id="50525-127">ad esempio include istruzioni su come creare un'applicazione del servizio Web ASP.NET utilizzabile per testare i servizi delle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="50525-127">For example, it includes instructions on how to create an ASP.NET Web Service Application that you can use to test client application services.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="50525-128">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="50525-128">Reference</span></span>  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## <a name="see-also"></a><span data-ttu-id="50525-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50525-129">See Also</span></span>  
 [<span data-ttu-id="50525-130">Cenni preliminari sui servizi delle applicazioni ASP.NET</span><span class="sxs-lookup"><span data-stu-id="50525-130">ASP.NET Application Services Overview</span></span>](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [<span data-ttu-id="50525-131">Uso dell'autenticazione basata su form con Microsoft Ajax</span><span class="sxs-lookup"><span data-stu-id="50525-131">Using Forms Authentication with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [<span data-ttu-id="50525-132">Uso delle informazioni sui ruoli con Microsoft Ajax</span><span class="sxs-lookup"><span data-stu-id="50525-132">Using Roles Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [<span data-ttu-id="50525-133">Uso delle informazioni sul profilo con Microsoft Ajax</span><span class="sxs-lookup"><span data-stu-id="50525-133">Using Profile Information with Microsoft Ajax</span></span>](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [<span data-ttu-id="50525-134">Autenticazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="50525-134">ASP.NET Authentication</span></span>](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 <span data-ttu-id="50525-135">[Gestione delle autorizzazioni tramite ruoli](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span><span class="sxs-lookup"><span data-stu-id="50525-135">[Managing Authorization Using Roles](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)  </span></span>  
 [<span data-ttu-id="50525-136">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="50525-136">Application Settings Overview</span></span>](../../../docs/framework/winforms/advanced/application-settings-overview.md)
