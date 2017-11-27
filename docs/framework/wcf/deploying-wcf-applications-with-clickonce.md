---
title: Distribuzione di applicazioni WCF con ClickOnce
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e7e419b1ca66e9d70b619e5841b8b984e06557f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="b611b-102">Distribuzione di applicazioni WCF con ClickOnce</span><span class="sxs-lookup"><span data-stu-id="b611b-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="b611b-103">Le applicazioni client che utilizzano [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] possono essere distribuite tramite la tecnologia ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="b611b-103">Client applications using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="b611b-104">Questa tecnologia consente loro di avvalersi delle protezioni runtime fornite dalla protezione dall'accesso di codice, purché siano firmate digitalmente con un certificato attendibile.</span><span class="sxs-lookup"><span data-stu-id="b611b-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="b611b-105">Il certificato utilizzato per firmare l'applicazione ClickOnce deve risiedere nell'archivio autori attendibili e il criterio di sicurezza locale nel computer client deve essere configurato per concedere autorizzazioni di attendibilità totale alle applicazioni firmate con il certificato dell'autore.</span><span class="sxs-lookup"><span data-stu-id="b611b-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="b611b-106">Per informazioni sulla configurazione di applicazioni ClickOnce e autori attendibili, vedere [la configurazione di editori attendibili ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="b611b-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b611b-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b611b-107">See Also</span></span>  
 [<span data-ttu-id="b611b-108">Panoramica della distribuzione di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="b611b-108">Trusted Application Deployment Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="b611b-109">Applicazioni di distribuzione ClickOnce per Windows Form</span><span class="sxs-lookup"><span data-stu-id="b611b-109">ClickOnce Deployment for Windows Forms Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=94776)
