---
title: Ciclo di vita della programmazione di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 78ad1159232ecfb75745dd72b7da1e3153a79574
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="266f6-102">Ciclo di vita della programmazione di base</span><span class="sxs-lookup"><span data-stu-id="266f6-102">Basic Programming Lifecycle</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="266f6-103"> consente alle applicazioni di comunicare nello stesso computer, in Internet o tra piattaforme di applicazione diverse.</span><span class="sxs-lookup"><span data-stu-id="266f6-103"> enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="266f6-104">In questo argomento vengono delineate le attività necessarie per compilare un'applicazione [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="266f6-104">This topic outlines the tasks that are required to build a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="266f6-105">Per un'applicazione di esempio funzionante, vedere [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="266f6-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="266f6-106">Attività di base</span><span class="sxs-lookup"><span data-stu-id="266f6-106">The Basic Tasks</span></span>  
 <span data-ttu-id="266f6-107">Le attività di base da eseguire sono descritte di seguito, in ordine progressivo:</span><span class="sxs-lookup"><span data-stu-id="266f6-107">The basic tasks to perform are, in order:</span></span>  
  
1.  <span data-ttu-id="266f6-108">Definire il contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="266f6-108">Define the service contract.</span></span> <span data-ttu-id="266f6-109">Un contratto di servizio specifica la firma di un servizio, i dati che scambia e altri dati necessari contrattualmente.</span><span class="sxs-lookup"><span data-stu-id="266f6-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="266f6-110">[Progettazione contratti di servizio](../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="266f6-110"> [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="266f6-111">Implementare il contratto.</span><span class="sxs-lookup"><span data-stu-id="266f6-111">Implement the contract.</span></span> <span data-ttu-id="266f6-112">Per implementare un contratto di servizio, creare una classe che implementa il contratto e specificare i comportamenti personalizzati per il runtime.</span><span class="sxs-lookup"><span data-stu-id="266f6-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="266f6-113">[Implementazione dei contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="266f6-113"> [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3.  <span data-ttu-id="266f6-114">Configurare il servizio specificando gli endpoint e le informazioni su altri comportamenti.</span><span class="sxs-lookup"><span data-stu-id="266f6-114">Configure the service by specifying endpoints and other behavior information.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="266f6-115">[Configurazione dei servizi](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="266f6-115"> [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4.  <span data-ttu-id="266f6-116">Ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="266f6-116">Host the service.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="266f6-117">[Servizi di hosting](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="266f6-117"> [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5.  <span data-ttu-id="266f6-118">Compilare un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="266f6-118">Build a client application.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="266f6-119">[Generazione di client](../../../docs/framework/wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="266f6-119"> [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="266f6-120">Anche se gli argomenti in questa sezione seguono questo ordine, alcuni scenari non partono dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="266f6-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="266f6-121">Ad esempio, se si desidera compilare un client per un servizio preesistente, iniziare dal passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="266f6-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="266f6-122">Se invece si compila un servizio che altri utilizzeranno, è possibile ignorare il passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="266f6-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="266f6-123">Una volta acquisita familiarità con lo sviluppo dei contratti di servizio, è inoltre possibile leggere [Introduzione all'estendibilità](../../../docs/framework/wcf/introduction-to-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="266f6-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="266f6-124">Se si verificano problemi con il servizio, controllare [Guida rapida risoluzione dei problemi di WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) per vedere se altri utenti hanno problemi identici o simili.</span><span class="sxs-lookup"><span data-stu-id="266f6-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="266f6-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="266f6-125">See Also</span></span>  
 [<span data-ttu-id="266f6-126">Implementazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="266f6-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)
