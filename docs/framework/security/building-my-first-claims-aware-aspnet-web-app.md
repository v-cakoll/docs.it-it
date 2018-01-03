---
title: Creazione della prima applicazione Web ASP.NET in grado di riconoscere attestazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 182f7c1646e112026852efcb5bb110607fe19360
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a><span data-ttu-id="43001-102">Creazione della prima applicazione Web ASP.NET in grado di riconoscere attestazioni</span><span class="sxs-lookup"><span data-stu-id="43001-102">Building My First Claims-Aware ASP.NET Web Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="43001-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="43001-103">Applies To</span></span>  
  
-   <span data-ttu-id="43001-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="43001-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="43001-105">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43001-105">ASP.NET</span></span>  
  
 <span data-ttu-id="43001-106">In questo argomento viene illustrato lo scenario di compilazione di applicazioni Web ASP.NET in grado di riconoscere attestazioni mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="43001-106">This topic outlines the scenario of building claims-aware ASP.NET web applications using WIF.</span></span> <span data-ttu-id="43001-107">Uno scenario di applicazione in grado di riconoscere attestazioni prevede in genere tre partecipanti: l'applicazione stessa, l'utente finale e il servizio token di sicurezza,</span><span class="sxs-lookup"><span data-stu-id="43001-107">There are usually three participants in a claims-aware application scenario: the application itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="43001-108">come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="43001-108">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="43001-109">![App Web di base WIF](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")</span><span class="sxs-lookup"><span data-stu-id="43001-109">![WIF Basic Web App](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")</span></span>  
  
1.  <span data-ttu-id="43001-110">Tramite l'applicazione in grado di riconoscere attestazioni viene utilizzato WIF per identificare le richieste non autenticate e per reindirizzarle al servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="43001-110">The claims-aware application uses WIF to identify unauthenticated requests and to redirect them to the STS.</span></span>  
  
2.  <span data-ttu-id="43001-111">L'utente finale fornisce le credenziali al servizio token di sicurezza e alla riuscita dell'autenticazione all'utente viene rilasciato un token dal servizio in questione.</span><span class="sxs-lookup"><span data-stu-id="43001-111">The end user provides credentials to the STS and upon successful authentication the user is issued a token by the STS.</span></span>  
  
3.  <span data-ttu-id="43001-112">L'utente viene reindirizzato dal servizio token di sicurezza all'applicazione in grado di riconoscere attestazioni con il token rilasciato da questo servizio nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="43001-112">The user is redirected from the STS to the claims-aware application with the STS-issued token in the request.</span></span>  
  
4.  <span data-ttu-id="43001-113">L'applicazione in grado di riconoscere attestazioni viene configurata per considerare attendibili il servizio token di sicurezza e i token da quest'ultimo rilasciati.</span><span class="sxs-lookup"><span data-stu-id="43001-113">The claims-aware application is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="43001-114">Tramite l'applicazione in grado di riconoscere attestazioni viene utilizzato WIF per convalidare il token e analizzarlo.</span><span class="sxs-lookup"><span data-stu-id="43001-114">The claims-aware application uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="43001-115">Gli sviluppatori usano tipi e API WIF appropriati, ad esempio **ClaimsPrincipal**, per esigenze dell'applicazione come l'implementazione della relativa autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="43001-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincpal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="43001-116">A partire da .NET 4.5, WIF fa parte del pacchetto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="43001-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="43001-117">La disponibilità delle classi di WIF direttamente nel framework consente una maggiore integrazione dell'identità basata sulle attestazioni nella piattaforma .NET, semplificando l'utilizzo delle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="43001-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="43001-118">Con WIF 4.5 non è necessario installare altri componenti fuori banda per avviare lo sviluppo di applicazioni Web in grado di riconoscere attestazioni.</span><span class="sxs-lookup"><span data-stu-id="43001-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="43001-119">Le classi di WIF vengono ora estese tra diversi assembly, i principali dei quali sono System.Security.Claims, System.IdentityModel e System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="43001-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="43001-120">Il servizio token di sicurezza è un servizio tramite cui vengono rilasciati dei token alla riuscita dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="43001-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="43001-121">Microsoft offre due servizi token di sicurezza standard del settore:</span><span class="sxs-lookup"><span data-stu-id="43001-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   <span data-ttu-id="43001-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span><span class="sxs-lookup"><span data-stu-id="43001-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span></span>  
  
-   <span data-ttu-id="43001-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span><span class="sxs-lookup"><span data-stu-id="43001-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span></span>  
  
 <span data-ttu-id="43001-124">AD FS 2.0 fa parte di Windows Server R2 e può essere utilizzato come servizio token di sicurezza in scenari locali.</span><span class="sxs-lookup"><span data-stu-id="43001-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="43001-125">ACS è un servizio cloud, fornito come parte della piattaforma Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="43001-125">ACS is a cloud service, offered as part of the Windows Azure Platform.</span></span> <span data-ttu-id="43001-126">Per fini di test e didattici, è inoltre possibile utilizzare altri servizi token di sicurezza per compilare applicazioni in grado di riconoscere attestazioni.</span><span class="sxs-lookup"><span data-stu-id="43001-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="43001-127">È possibile, ad esempio, usare il servizio token di sicurezza di sviluppo locale che fa parte di [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849), disponibile gratuitamente online.</span><span class="sxs-lookup"><span data-stu-id="43001-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="43001-128">Per compilare la prima applicazione ASP.NET in grado di riconoscere attestazioni mediante WIF, seguire le istruzioni in uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="43001-128">To build your first claims-aware ASP.NET application using WIF, follow the instructions in one of the following:</span></span>  
  
-   [<span data-ttu-id="43001-129">Procedura: Compilare un'applicazione Web ASP.NET MVC che può riconoscere attestazioni con WIF</span><span class="sxs-lookup"><span data-stu-id="43001-129">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [<span data-ttu-id="43001-130">Procedura: Compilare un'applicazione Web Form ASP.NET che può riconoscere attestazioni con WIF</span><span class="sxs-lookup"><span data-stu-id="43001-130">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [<span data-ttu-id="43001-131">Procedura: Compilare un'applicazione ASP.NET che può riconoscere attestazioni con l'autenticazione basata su moduli</span><span class="sxs-lookup"><span data-stu-id="43001-131">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="43001-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43001-132">See Also</span></span>  
 [<span data-ttu-id="43001-133">Guida introduttiva a WIF</span><span class="sxs-lookup"><span data-stu-id="43001-133">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
