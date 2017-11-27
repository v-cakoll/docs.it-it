---
title: WCF Discovery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fda50f14d9003b81f93840571b8b27f874f7730b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-discovery"></a><span data-ttu-id="4b32d-102">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="4b32d-102">WCF Discovery</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="4b32d-103"> fornisce il supporto per l'individuabilità dei servizi in fase di esecuzione in una modalità interoperativa utilizzando il protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="4b32d-103"> provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="4b32d-104">I servizi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono annunciare la disponibilità alla rete utilizzando un messaggio multicast o a un server proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="4b32d-104">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="4b32d-105">Le applicazioni client possono eseguire ricerche nella rete o in un server proxy di individuazione per trovare servizi che soddisfano un set di criteri.</span><span class="sxs-lookup"><span data-stu-id="4b32d-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="4b32d-106">Negli argomenti di questa sezione viene fornita una panoramica e viene proposta una descrizione dettagliata del modello di programmazione per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4b32d-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b32d-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4b32d-107">In This Section</span></span>  
 [<span data-ttu-id="4b32d-108">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="4b32d-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="4b32d-109">Fornisce una panoramica del supporto WS-Discovery fornito da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b32d-109">Provides an overview of WS-Discovery support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="4b32d-110">Modello a oggetti WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="4b32d-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="4b32d-111">Descrive le classi nel modello a oggetti e l'estensibilità del supporto WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="4b32d-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="4b32d-112">Procedura: aggiungere a livello di programmazione esposizione al rilevamento a un servizio WCF e un Client</span><span class="sxs-lookup"><span data-stu-id="4b32d-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="4b32d-113">Mostra come rendere individuabile un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b32d-113">Shows how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span>  
  
 [<span data-ttu-id="4b32d-114">Implementazione di un Proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="4b32d-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="4b32d-115">Descrive i passaggi richiesti per implementare un proxy di individuazione, un servizio individuabile che esegue la registrazione al proxy di individuazione e un client che utilizza il proxy di individuazione per trovare il servizio individuabile.</span><span class="sxs-lookup"><span data-stu-id="4b32d-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="4b32d-116">Controllo delle versioni di individuazione</span><span class="sxs-lookup"><span data-stu-id="4b32d-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="4b32d-117">Fornisce una breve panoramica di un'implementazione del prototipo di alcune nuove funzionalità di individuazione.</span><span class="sxs-lookup"><span data-stu-id="4b32d-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="4b32d-118">Vengono inoltre forniti cenni preliminari sulla scelta della versione dell'individuazione da usare.</span><span class="sxs-lookup"><span data-stu-id="4b32d-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="4b32d-119">Configurazione dell'individuazione in un File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4b32d-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="4b32d-120">Mostra come configurare la funzionalità di individuazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="4b32d-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="4b32d-121">Utilizzo del canale Client di individuazione</span><span class="sxs-lookup"><span data-stu-id="4b32d-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="4b32d-122">Mostra come utilizzare un canale client di individuazione in caso di scrittura di un'applicazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b32d-122">Shows how to use a Discovery Client Channel when writing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span>
