---
title: Distribuzione di un progetto Libreria di servizi WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbbbff1d88559f8ab35caa48fcb04ff1cd7bf015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-a-wcf-library-project"></a><span data-ttu-id="64dba-102">Distribuzione di un progetto Libreria di servizi WCF</span><span class="sxs-lookup"><span data-stu-id="64dba-102">Deploying a WCF Library Project</span></span>
<span data-ttu-id="64dba-103">Questo argomento descrive come distribuire un progetto Libreria di servizi [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64dba-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Library Project.</span></span>  
  
## <a name="deploying-a-wcf-service-library"></a><span data-ttu-id="64dba-104">Distribuzione di una libreria di servizi WCF</span><span class="sxs-lookup"><span data-stu-id="64dba-104">Deploying a WCF Service Library</span></span>  
 <span data-ttu-id="64dba-105">Una libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è una libreria di collegamento dinamico (DLL, Dynamic Link Library).</span><span class="sxs-lookup"><span data-stu-id="64dba-105">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library is a dynamic-link library (DLL).</span></span> <span data-ttu-id="64dba-106">In quanto tale, non può essere eseguita autonomamente:</span><span class="sxs-lookup"><span data-stu-id="64dba-106">As such, it cannot be executed on its own.</span></span> <span data-ttu-id="64dba-107">deve essere distribuita in un ambiente host.</span><span class="sxs-lookup"><span data-stu-id="64dba-107">It needs to be deployed into a hosting environment.</span></span> <span data-ttu-id="64dba-108">Per ulteriori informazioni su questo processo, vedere [Hosting e l'utilizzo di servizi WCF](http://go.microsoft.com/fwlink/?LinkId=99932).</span><span class="sxs-lookup"><span data-stu-id="64dba-108">For more information about this process, see [Hosting and Consuming WCF Services](http://go.microsoft.com/fwlink/?LinkId=99932).</span></span>  
  
 <span data-ttu-id="64dba-109">Una libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] può essere distribuita come qualsiasi altro servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64dba-109">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library can be deployed like any other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="64dba-110">Tuttavia, occorre tenere presente che [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] non supporta la configurazione di DLL.</span><span class="sxs-lookup"><span data-stu-id="64dba-110">However, be aware that [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] does not support configuration for DLLs.</span></span> <span data-ttu-id="64dba-111"><xref:System.Configuration> supporta un unico file di configurazione per ogni dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="64dba-111"><xref:System.Configuration> supports one configuration file per app-domain.</span></span> <span data-ttu-id="64dba-112">Il progetto Libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] riduce questa limitazione fornendo durante lo sviluppo un file per la libreria denominato App.config.</span><span class="sxs-lookup"><span data-stu-id="64dba-112">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library project alleviates this limitation by providing an App.config file for the library during development.</span></span> <span data-ttu-id="64dba-113">Dopo la distribuzione, tuttavia, il file App.config non viene riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="64dba-113">However, the App.config file is not recognized after deployment.</span></span>  
  
 <span data-ttu-id="64dba-114">È necessario spostare il codice di configurazione nel file di configurazione riconosciuto dall'ambiente host utilizzato.</span><span class="sxs-lookup"><span data-stu-id="64dba-114">You have to move your configuration code into the configuration file recognized by your hosting environment.</span></span> <span data-ttu-id="64dba-115">Nel caso di servizi indipendenti, è necessario copiare il contenuto del file App.config nel file App.config del file eseguibile di hosting.</span><span class="sxs-lookup"><span data-stu-id="64dba-115">For self-hosting, you should copy the contents of the App.config file into the App.config file of the hosting executable.</span></span> <span data-ttu-id="64dba-116">Se per l'hosting del servizio si utilizza IIS, è necessario copiare il contenuto del file App.config nel file Web.config della directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="64dba-116">If you use IIS to host your service, you should copy the contents of the App.config file into the Web.config file of the virtual directory.</span></span>
