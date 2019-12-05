---
title: Distribuzione di applicazioni WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: b520931751bbba00d440b46657962ad3f1e41cd3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802230"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="e8a57-102">Distribuzione di applicazioni WCF con ClickOnce</span><span class="sxs-lookup"><span data-stu-id="e8a57-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="e8a57-103">Le applicazioni client che utilizzano Windows Communication Foundation (WCF) possono essere distribuite utilizzando la tecnologia ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="e8a57-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="e8a57-104">Questa tecnologia consente loro di avvalersi delle protezioni runtime fornite dalla protezione dall'accesso di codice, purché siano firmate digitalmente con un certificato attendibile.</span><span class="sxs-lookup"><span data-stu-id="e8a57-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="e8a57-105">Il certificato utilizzato per firmare l'applicazione ClickOnce deve risiedere nell'archivio autori attendibili e il criterio di sicurezza locale nel computer client deve essere configurato per concedere autorizzazioni di attendibilità totale alle applicazioni firmate con il certificato dell'autore.</span><span class="sxs-lookup"><span data-stu-id="e8a57-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="e8a57-106">Per informazioni sulla configurazione di applicazioni ClickOnce e autori attendibili, vedere la pagina relativa alla [configurazione di editori attendibili ClickOnce](https://docs.microsoft.com/previous-versions/dotnet/articles/ms996418(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="e8a57-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](https://docs.microsoft.com/previous-versions/dotnet/articles/ms996418(v=msdn.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a57-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8a57-107">See also</span></span>

- [<span data-ttu-id="e8a57-108">Panoramica della distribuzione di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="e8a57-108">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)
- <span data-ttu-id="e8a57-109">[Distribuzione ClickOnce per applicazioni Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e8a57-109">[ClickOnce Deployment for Windows Forms Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))</span></span>
