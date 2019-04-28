---
title: WCF Discovery
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 175f79096d2bbda81a602d38e027d5a6d871fa12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768693"
---
# <a name="wcf-discovery"></a><span data-ttu-id="fbf91-102">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="fbf91-102">WCF Discovery</span></span>
<span data-ttu-id="fbf91-103">Windows Communication Foundation (WCF) fornisce il supporto per abilitare servizi individuabili in fase di esecuzione in una modalità interoperativa utilizzando il protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="fbf91-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="fbf91-104">Servizi WCF possono annunciare la disponibilità alla rete utilizzando un messaggio multicast o a un server proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="fbf91-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="fbf91-105">Le applicazioni client possono eseguire ricerche nella rete o in un server proxy di individuazione per trovare servizi che soddisfano un set di criteri.</span><span class="sxs-lookup"><span data-stu-id="fbf91-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="fbf91-106">Negli argomenti di questa sezione viene fornita una panoramica e viene proposta una descrizione dettagliata del modello di programmazione per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="fbf91-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbf91-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="fbf91-107">In This Section</span></span>  
 [<span data-ttu-id="fbf91-108">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="fbf91-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="fbf91-109">Fornisce una panoramica del supporto WS-Discovery fornito da WCF.</span><span class="sxs-lookup"><span data-stu-id="fbf91-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="fbf91-110">Modello a oggetti WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="fbf91-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="fbf91-111">Descrive le classi nel modello a oggetti e l'estensibilità del supporto WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="fbf91-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="fbf91-112">Procedura: A livello di codice aggiungere funzionalità di individuazione a un Client e servizio WCF</span><span class="sxs-lookup"><span data-stu-id="fbf91-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="fbf91-113">Viene illustrato come rendere individuabile un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fbf91-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="fbf91-114">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="fbf91-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="fbf91-115">Descrive i passaggi richiesti per implementare un proxy di individuazione, un servizio individuabile che esegue la registrazione al proxy di individuazione e un client che utilizza il proxy di individuazione per trovare il servizio individuabile.</span><span class="sxs-lookup"><span data-stu-id="fbf91-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="fbf91-116">Controllo delle versioni per l'individuazione</span><span class="sxs-lookup"><span data-stu-id="fbf91-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="fbf91-117">Fornisce una breve panoramica di un'implementazione del prototipo di alcune nuove funzionalità di individuazione.</span><span class="sxs-lookup"><span data-stu-id="fbf91-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="fbf91-118">Vengono inoltre forniti cenni preliminari sulla scelta della versione dell'individuazione da usare.</span><span class="sxs-lookup"><span data-stu-id="fbf91-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="fbf91-119">Configurazione dell'individuazione in un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="fbf91-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="fbf91-120">Mostra come configurare la funzionalità di individuazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="fbf91-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="fbf91-121">Utilizzo del canale client di individuazione</span><span class="sxs-lookup"><span data-stu-id="fbf91-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="fbf91-122">Viene illustrato come utilizzare un canale Client di individuazione durante la scrittura di un'applicazione client WCF.</span><span class="sxs-lookup"><span data-stu-id="fbf91-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
