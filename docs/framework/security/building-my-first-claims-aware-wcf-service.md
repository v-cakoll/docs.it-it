---
title: "Creazione del primo servizio WCF che può riconoscere attestazioni"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 791c86b8f833c6b1a8acb6da3b03cfccdafca0e5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="building-my-first-claims-aware-wcf-service"></a><span data-ttu-id="22771-102">Creazione del primo servizio WCF che può riconoscere attestazioni</span><span class="sxs-lookup"><span data-stu-id="22771-102">Building My First Claims-Aware WCF Service</span></span>
## <a name="applies-to"></a><span data-ttu-id="22771-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="22771-103">Applies To</span></span>  
  
-   <span data-ttu-id="22771-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="22771-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="22771-105">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="22771-105">Windows Communication Foundation (WCF)</span></span>  
  
## <a name="overview"></a><span data-ttu-id="22771-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="22771-106">Overview</span></span>  
 <span data-ttu-id="22771-107">In questo argomento viene illustrato lo scenario di compilazione di servizi WCF in grado di riconoscere attestazioni mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="22771-107">This topic outlines the scenario of building claims-aware WCF services using WIF.</span></span> <span data-ttu-id="22771-108">Uno scenario di servizio Web in grado di riconoscere attestazioni è in genere caratterizzato da tre partecipanti: il servizio Web stesso, l'utente finale e il servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="22771-108">There are usually three participants in a claims-aware web service scenario: the web service itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="22771-109">come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="22771-109">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="22771-110">![Servizio WCF in grado di riconoscere attestazioni di base WIF](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span><span class="sxs-lookup"><span data-stu-id="22771-110">![WIF Basic Claims Aware WCF Service](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span></span>  
  
1.  <span data-ttu-id="22771-111">Tramite il client del servizio WCF (talvolta definito agente) viene utilizzato WIF per inviare le credenziali al servizio token di sicurezza e alla riuscita dell'autenticazione, tramite l'agente viene emesso un token dal servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="22771-111">The WCF service client (sometimes called agent) uses WIF to send credentials to the STS and upon successful authentication, the agent is issued a token by the STS.</span></span>  
  
2.  <span data-ttu-id="22771-112">L'agente invia questo token emesso dal servizio token di sicurezza al servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="22771-112">The agent sends this STS-issued token to the WCF service.</span></span>  
  
3.  <span data-ttu-id="22771-113">Il servizio WCF in grado di riconoscere attestazioni viene configurato per considerare attendibili il servizio token di sicurezza e i token da quest'ultimo emessi.</span><span class="sxs-lookup"><span data-stu-id="22771-113">The claims-aware WCF service is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="22771-114">Tramite il servizio WCF in grado di riconoscere attestazioni viene utilizzato WIF per convalidare il token e analizzarlo.</span><span class="sxs-lookup"><span data-stu-id="22771-114">The claims-aware WCF service uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="22771-115">Gli sviluppatori usano tipi e API WIF appropriati, ad esempio **ClaimsPrincipal**, per esigenze dell'applicazione come l'implementazione della relativa autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="22771-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincipal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="22771-116">A partire da .NET 4.5, WIF fa parte del pacchetto .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22771-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="22771-117">La disponibilità delle classi di WIF direttamente nel framework consente una maggiore integrazione dell'identità basata sulle attestazioni nella piattaforma .NET, semplificando l'utilizzo delle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="22771-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="22771-118">Con WIF 4.5 non è necessario installare altri componenti fuori banda per avviare lo sviluppo di applicazioni Web in grado di riconoscere attestazioni.</span><span class="sxs-lookup"><span data-stu-id="22771-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="22771-119">Le classi di WIF vengono ora estese tra diversi assembly, i principali dei quali sono System.Security.Claims, System.IdentityModel e System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="22771-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="22771-120">Il servizio token di sicurezza è un servizio tramite cui vengono rilasciati dei token alla riuscita dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="22771-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="22771-121">Microsoft offre due servizi token di sicurezza standard del settore:</span><span class="sxs-lookup"><span data-stu-id="22771-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   <span data-ttu-id="22771-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span><span class="sxs-lookup"><span data-stu-id="22771-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span></span>  
  
-   <span data-ttu-id="22771-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span><span class="sxs-lookup"><span data-stu-id="22771-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span></span>  
  
 <span data-ttu-id="22771-124">AD FS 2.0 fa parte di Windows Server R2 e può essere utilizzato come servizio token di sicurezza in scenari locali.</span><span class="sxs-lookup"><span data-stu-id="22771-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="22771-125">Azure Active Directory Access Control (detto anche Servizio di controllo di accesso o ACS) è un servizio cloud, fornito come parte di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="22771-125">Azure Active Directory Access Control (also known as Access Control Service or ACS) is a cloud service, offered as part of Microsoft Azure.</span></span> <span data-ttu-id="22771-126">Per fini di test e didattici, è inoltre possibile utilizzare altri servizi token di sicurezza per compilare applicazioni in grado di riconoscere attestazioni.</span><span class="sxs-lookup"><span data-stu-id="22771-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="22771-127">È possibile, ad esempio, usare il servizio token di sicurezza di sviluppo locale che fa parte di [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849), disponibile gratuitamente online.</span><span class="sxs-lookup"><span data-stu-id="22771-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="22771-128">Per compilare il primo servizio WCF in grado di riconoscere attestazioni mediante l'utilizzo di WIF, vedere [Procedura: Compilare un servizio WCF in grado di riconoscere attestazioni mediante WIF](http://msdn.microsoft.com/library/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).</span><span class="sxs-lookup"><span data-stu-id="22771-128">To build your first claims-aware WCF service using WIF, see [How To: Build Claims-Aware WCF Service Using WIF](http://msdn.microsoft.com/library/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22771-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22771-129">See Also</span></span>  
 [<span data-ttu-id="22771-130">Guida introduttiva a WIF</span><span class="sxs-lookup"><span data-stu-id="22771-130">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
