---
title: Distribuzione di applicazioni WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: d733c6f523393737418c6394707c1d4e6e9c1710
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45590494"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="25660-102">Distribuzione di applicazioni WCF con ClickOnce</span><span class="sxs-lookup"><span data-stu-id="25660-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="25660-103">Le applicazioni client tramite Windows Communication Foundation (WCF) possono essere distribuite tramite la tecnologia ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="25660-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="25660-104">Questa tecnologia consente loro di avvalersi delle protezioni runtime fornite dalla protezione dall'accesso di codice, purché siano firmate digitalmente con un certificato attendibile.</span><span class="sxs-lookup"><span data-stu-id="25660-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="25660-105">Il certificato utilizzato per firmare l'applicazione ClickOnce deve risiedere nell'archivio autori attendibili e il criterio di sicurezza locale nel computer client deve essere configurato per concedere autorizzazioni di attendibilità totale alle applicazioni firmate con il certificato dell'autore.</span><span class="sxs-lookup"><span data-stu-id="25660-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="25660-106">Per informazioni sulla configurazione di applicazioni ClickOnce e autori attendibili, vedere [configurazione di editori attendibili ClickOnce](https://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="25660-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](https://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25660-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25660-107">See Also</span></span>  
 [<span data-ttu-id="25660-108">Panoramica della distribuzione di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="25660-108">Trusted Application Deployment Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="25660-109">Distribuzione ClickOnce per Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="25660-109">ClickOnce Deployment for Windows Forms Applications</span></span>](https://go.microsoft.com/fwlink/?LinkId=94776)
