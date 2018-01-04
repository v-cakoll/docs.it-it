---
title: Estensione di ServiceHost e del livello del modello di servizi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c73af3b9187fa5365d7ea99474ea182d5f5ae86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a><span data-ttu-id="d7ea2-102">Estensione di ServiceHost e del livello del modello di servizi</span><span class="sxs-lookup"><span data-stu-id="d7ea2-102">Extending ServiceHost and the Service Model Layer</span></span>
<span data-ttu-id="d7ea2-103">Il livello del modello di servizi è responsabile del pull dei messaggi in arrivo dai canali sottostanti, della loro conversione in chiamate al metodo nel codice dell'applicazione e della restituzione dei risultati al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-103">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span> <span data-ttu-id="d7ea2-104">Le estensioni del modello di servizi modificano o implementano il comportamento e le funzionalità dell'esecuzione o della comunicazione relativamente a funzionalità del client o del dispatcher, comportamenti personalizzati, intercettazione di messaggi e parametri e altre funzionalità di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-104">Service model extensions modify or implement execution or communication behavior and features involving client or dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7ea2-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d7ea2-105">In This Section</span></span>  
 [<span data-ttu-id="d7ea2-106">Estensione dei client</span><span class="sxs-lookup"><span data-stu-id="d7ea2-106">Extending Clients</span></span>](../../../../docs/framework/wcf/extending/extending-clients.md)  
 <span data-ttu-id="d7ea2-107">Vengono descritte le interfacce in grado di intercettare e modificare la fase di esecuzione del client, nonché le classi nelle quali è possibile inserire estensioni personalizzate nelle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-107">Describes the interfaces that can intercept and modify the client runtime, as well as the classes into which you can insert your custom extensions in client applications.</span></span> <span data-ttu-id="d7ea2-108">È ad esempio possibile eseguire la registrazione dei messaggi del client personalizzata, la serializzazione dei messaggi personalizzata e così via.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-108">For example, you can perform custom client message logging, perform custom message serialization, and so on.</span></span>  
  
 [<span data-ttu-id="d7ea2-109">Estensione di dispatcher</span><span class="sxs-lookup"><span data-stu-id="d7ea2-109">Extending Dispatchers</span></span>](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 <span data-ttu-id="d7ea2-110">Vengono descritte le interfacce in grado di intercettare e modificare la fase di esecuzione del servizio, nonché le classi nelle quali è possibile inserire estensioni personalizzate nelle applicazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-110">Describes the interfaces that can intercept and modify the service runtime, as well as the classes into which you can insert your custom extensions in service applications.</span></span> <span data-ttu-id="d7ea2-111">È ad esempio possibile eseguire la registrazione del servizio personalizzata, la convalida dei messaggi dal lato del servizio, la distribuzione personalizzata e così via.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-111">For example, you can perform custom service logging, service-side message validation, custom dispatching, and so on.</span></span>  
  
 [<span data-ttu-id="d7ea2-112">Oggetti estensibili</span><span class="sxs-lookup"><span data-stu-id="d7ea2-112">Extensible Objects</span></span>](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 <span data-ttu-id="d7ea2-113">Vengono descritti i cinque oggetti estendibili e il modello <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-113">Describes the five extensible objects and the <xref:System.ServiceModel.IExtensibleObject%601> pattern.</span></span> <span data-ttu-id="d7ea2-114">Questo modello viene usato per estendere le classi di runtime esistenti con nuove funzionalità oppure per aggiungere un nuovo stato a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-114">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="d7ea2-115">Le estensioni, allegate a uno degli oggetti estensibili, attivano i comportamenti in fasi molto diverse dell'elaborazione per accedere a stato e funzionalità condivisi allegati a un oggetto estensibile comune al quale possono accedere.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-115">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
 [<span data-ttu-id="d7ea2-116">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="d7ea2-116">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 <span data-ttu-id="d7ea2-117">Per modificare le impostazioni o per inserire estensioni nella fase di esecuzione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si utilizzano i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-117">To change settings on or insert extensions in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime, you use Behaviors.</span></span> <span data-ttu-id="d7ea2-118">WCF comprende comportamenti implementati dal sistema per controllare la limitazione delle richieste, la creazione di istanze e molti altri aspetti di servizi e operazioni.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-118">WCF includes system-implemented behaviors for controlling throttling, instancing, and many other aspects of services and operations.</span></span> <span data-ttu-id="d7ea2-119">Contenuto della sezione viene descritto come creare comportamenti personalizzati e come renderli disponibili per l'utilizzo sia a livello di programmazione che nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-119">This section describes how to create your own custom behaviors and how to make them available for use both programmatically and using configuration files.</span></span>  
  
 [<span data-ttu-id="d7ea2-120">Estensione dell'hosting tramite ServiceHostFactory</span><span class="sxs-lookup"><span data-stu-id="d7ea2-120">Extending Hosting Using ServiceHostFactory</span></span>](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 <span data-ttu-id="d7ea2-121">Viene descritto come estendere <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> e come utilizzare le classi <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> per personalizzare l'ambiente host.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-121">Describes how to extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, and use the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> classes to customize the host environment.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d7ea2-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="d7ea2-122">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d7ea2-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d7ea2-123">Related Sections</span></span>
