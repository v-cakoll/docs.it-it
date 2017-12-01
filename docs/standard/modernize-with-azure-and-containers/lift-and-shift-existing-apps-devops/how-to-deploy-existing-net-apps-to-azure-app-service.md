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
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a>Come distribuire le app .NET esistenti in Azure App Service 

La funzionalità di App Web di Azure App Service è una piattaforma di calcolo completamente gestito che è ottimizzata per l'hosting di applicazioni e i siti web. Questa offerta PaaS consente a Microsoft Azure è concentrarsi sulla logica di business, mentre Azure si occupa dell'infrastruttura per l'esecuzione e ridimensionare le app.

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a>Convalidare i siti e la migrazione al servizio App con Azure App Service Migration Assistant

Quando si crea una nuova applicazione in Visual Studio, lo spostamento dell'app al servizio App in genere è semplice. Tuttavia, se si intende eseguire la migrazione di un'applicazione di servizio App esistente, è necessario valutare se tutte le dipendenze dell'applicazione sono compatibili con il servizio App. Include le dipendenze come server del sistema operativo e qualsiasi software di terze parti installato sul server.

È possibile utilizzare [Migration Assistant di Azure App Service](https://www.migratetoazure.net/) per analizzare i siti e quindi eseguirne la migrazione dal server web di Windows e Linux nel servizio App. Come parte della migrazione, lo strumento crea App web e i database in Azure in base alle esigenze, pubblica il contenuto e pubblica il database.

Azure App Service Migration Assistant supporta la migrazione da IIS in esecuzione in Windows Server nel cloud. Servizio App supporta Windows Server 2003 e versioni successive.

> ![https://www.migratetoazure.NET/Images/ImageCanvas.PNG](./media/image5.png)
>
> **Figura 4-5.** Utilizzo di servizio App di Azure Migration Assistant

Migration Assistant App del servizio è uno strumento che consente di spostare i siti Web dai server web nel cloud di Azure.

Dopo la migrazione di un sito Web al servizio App, il sito dispone di tutto il che necessario per eseguire in modo sicuro ed efficiente. Siti vengono impostati e viene eseguiti automaticamente nel servizio cloud di Azure PaaS (servizio App).

Lo strumento di migrazione del servizio App consentono di analizzare i siti Web e di report sulla compatibilità per lo spostamento al servizio App. Se si è soddisfatti dell'analisi, è possibile consentire App servizio Migration Assistant migrazione del contenuto, dati e impostazioni. Se un sito non è abbastanza compatibile, lo strumento di migrazione indica ciò che è necessario modificare per utilizzarlo.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Migration Assistant di servizio App di Azure**

    [https://www.migratetoazure.NET/](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
[Precedente](what-about-cloud-optimized-applications.md)
[Successivo](deploy-existing-net-apps-as-windows-containers.md)
