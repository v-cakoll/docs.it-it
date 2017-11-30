---
title: Come distribuire le app .NET esistenti in Azure App Service
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Come distribuire le app .NET esistenti in Azure App Service
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: c83703c6f3dede0f92263e0d46bf48525c3eefaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a><span data-ttu-id="1508d-103">Come distribuire le app .NET esistenti in Azure App Service</span><span class="sxs-lookup"><span data-stu-id="1508d-103">How to deploy existing .NET apps to Azure App Service</span></span> 

<span data-ttu-id="1508d-104">La funzionalità di App Web di Azure App Service è una piattaforma di calcolo completamente gestito che è ottimizzata per l'hosting di applicazioni e i siti web.</span><span class="sxs-lookup"><span data-stu-id="1508d-104">The Web Apps feature of Azure App Service is a fully managed compute platform that is optimized for hosting websites and web apps.</span></span> <span data-ttu-id="1508d-105">Questa offerta PaaS consente a Microsoft Azure è concentrarsi sulla logica di business, mentre Azure si occupa dell'infrastruttura per l'esecuzione e ridimensionare le app.</span><span class="sxs-lookup"><span data-stu-id="1508d-105">This PaaS offering in Microsoft Azure lets you focus on your business logic, while Azure takes care of the infrastructure to run and scale your apps.</span></span>

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a><span data-ttu-id="1508d-106">Convalidare i siti e la migrazione al servizio App con Azure App Service Migration Assistant</span><span class="sxs-lookup"><span data-stu-id="1508d-106">Validate sites and migrate to App Service with Azure App Service Migration Assistant</span></span>

<span data-ttu-id="1508d-107">Quando si crea una nuova applicazione in Visual Studio, lo spostamento dell'app al servizio App in genere è semplice.</span><span class="sxs-lookup"><span data-stu-id="1508d-107">When you create a new application in Visual Studio, moving the app to App Service usually is straightforward.</span></span> <span data-ttu-id="1508d-108">Tuttavia, se si intende eseguire la migrazione di un'applicazione di servizio App esistente, è necessario valutare se tutte le dipendenze dell'applicazione sono compatibili con il servizio App.</span><span class="sxs-lookup"><span data-stu-id="1508d-108">However, if you are planning to migrate an existing application to App Service, first you need to evaluate whether all your application's dependencies are compatible with App Service.</span></span> <span data-ttu-id="1508d-109">Include le dipendenze come server del sistema operativo e qualsiasi software di terze parti installato sul server.</span><span class="sxs-lookup"><span data-stu-id="1508d-109">This includes dependencies like server OS and any third-party software that's installed on the server.</span></span>

<span data-ttu-id="1508d-110">È possibile utilizzare [Migration Assistant di Azure App Service](https://www.migratetoazure.net/) per analizzare i siti e quindi eseguirne la migrazione dal server web di Windows e Linux nel servizio App.</span><span class="sxs-lookup"><span data-stu-id="1508d-110">You can use [Azure App Service Migration Assistant](https://www.migratetoazure.net/) to analyze sites and then migrate them from Windows and Linux web servers to App Service.</span></span> <span data-ttu-id="1508d-111">Come parte della migrazione, lo strumento crea App web e i database in Azure in base alle esigenze, pubblica il contenuto e pubblica il database.</span><span class="sxs-lookup"><span data-stu-id="1508d-111">As part of the migration, the tool creates web apps and databases on Azure as needed, publishes content, and publishes your database.</span></span>

<span data-ttu-id="1508d-112">Azure App Service Migration Assistant supporta la migrazione da IIS in esecuzione in Windows Server nel cloud.</span><span class="sxs-lookup"><span data-stu-id="1508d-112">Azure App Service Migration Assistant supports migrating from IIS running on Windows Server to the cloud.</span></span> <span data-ttu-id="1508d-113">Servizio App supporta Windows Server 2003 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="1508d-113">App Service supports Windows Server 2003 and later versions.</span></span>

> ![https://www.migratetoazure.NET/Images/ImageCanvas.PNG](./media/image5.png)
>
> <span data-ttu-id="1508d-115">**Figura 4-5.**</span><span class="sxs-lookup"><span data-stu-id="1508d-115">**Figure 4-5.**</span></span> <span data-ttu-id="1508d-116">Utilizzo di servizio App di Azure Migration Assistant</span><span class="sxs-lookup"><span data-stu-id="1508d-116">Using Azure App Service Migration Assistant</span></span>

<span data-ttu-id="1508d-117">Migration Assistant App del servizio è uno strumento che consente di spostare i siti Web dai server web nel cloud di Azure.</span><span class="sxs-lookup"><span data-stu-id="1508d-117">App Service Migration Assistant is a tool that moves your websites from your web servers to the Azure cloud.</span></span>

<span data-ttu-id="1508d-118">Dopo la migrazione di un sito Web al servizio App, il sito dispone di tutto il che necessario per eseguire in modo sicuro ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="1508d-118">After a website is migrated to App Service, the site has everything it needs to run safely and efficiently.</span></span> <span data-ttu-id="1508d-119">Siti vengono impostati e viene eseguiti automaticamente nel servizio cloud di Azure PaaS (servizio App).</span><span class="sxs-lookup"><span data-stu-id="1508d-119">Sites are set up and run automatically in the Azure cloud PaaS service (App Service).</span></span>

<span data-ttu-id="1508d-120">Lo strumento di migrazione del servizio App consentono di analizzare i siti Web e di report sulla compatibilità per lo spostamento al servizio App.</span><span class="sxs-lookup"><span data-stu-id="1508d-120">The App Service migration tool can analyze your websites and report on their compatibility for moving to App Service.</span></span> <span data-ttu-id="1508d-121">Se si è soddisfatti dell'analisi, è possibile consentire App servizio Migration Assistant migrazione del contenuto, dati e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1508d-121">If you're happy with the analysis, you can let App Service Migration Assistant migrate content, data, and settings for you.</span></span> <span data-ttu-id="1508d-122">Se un sito non è abbastanza compatibile, lo strumento di migrazione indica ciò che è necessario modificare per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="1508d-122">If a site is not quite compatible, the migration tool tells you what you need to adjust to make it work.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1508d-123">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1508d-123">Additional resources</span></span>

-   <span data-ttu-id="1508d-124">**Migration Assistant di servizio App di Azure**</span><span class="sxs-lookup"><span data-stu-id="1508d-124">**Azure App Service Migration Assistant**</span></span>

    [<span data-ttu-id="1508d-125">https://www.migratetoazure.NET/</span><span class="sxs-lookup"><span data-stu-id="1508d-125">https://www.migratetoazure.net/</span></span>](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
<span data-ttu-id="1508d-126">[Precedente](what-about-cloud-optimized-applications.md)
[Successivo](deploy-existing-net-apps-as-windows-containers.md)</span><span class="sxs-lookup"><span data-stu-id="1508d-126">[Previous](what-about-cloud-optimized-applications.md)
[Next](deploy-existing-net-apps-as-windows-containers.md)</span></span>
