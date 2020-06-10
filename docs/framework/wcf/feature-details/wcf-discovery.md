---
title: WCF Discovery
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 63c6589cb2ecff9f0a5e7c8bb61b454f6516c98c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600179"
---
# <a name="wcf-discovery"></a><span data-ttu-id="e9bad-102">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="e9bad-102">WCF Discovery</span></span>
<span data-ttu-id="e9bad-103">Windows Communication Foundation (WCF) fornisce il supporto per consentire ai servizi di essere individuabili in fase di esecuzione in modo interoperativo utilizzando il protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="e9bad-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="e9bad-104">I servizi WCF possono annunciare la disponibilità alla rete utilizzando un messaggio multicast o a un server proxy di individuazione.</span><span class="sxs-lookup"><span data-stu-id="e9bad-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="e9bad-105">Le applicazioni client possono eseguire ricerche nella rete o in un server proxy di individuazione per trovare servizi che soddisfano un set di criteri.</span><span class="sxs-lookup"><span data-stu-id="e9bad-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="e9bad-106">Negli argomenti di questa sezione viene fornita una panoramica e viene proposta una descrizione dettagliata del modello di programmazione per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e9bad-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9bad-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e9bad-107">In This Section</span></span>  
 [<span data-ttu-id="e9bad-108">Panoramica di WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="e9bad-108">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)  
 <span data-ttu-id="e9bad-109">Viene fornita una panoramica del supporto WS-Discovery fornito da WCF.</span><span class="sxs-lookup"><span data-stu-id="e9bad-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="e9bad-110">Modello a oggetti WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="e9bad-110">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)  
 <span data-ttu-id="e9bad-111">Descrive le classi nel modello a oggetti e l'estensibilità del supporto WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="e9bad-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="e9bad-112">Procedura: aggiungere capacità di individuazione a un client e un servizio WCF a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e9bad-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="e9bad-113">Viene illustrato come rendere individuabile un servizio di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e9bad-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="e9bad-114">Implementazione di un proxy di individuazione</span><span class="sxs-lookup"><span data-stu-id="e9bad-114">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)  
 <span data-ttu-id="e9bad-115">Descrive i passaggi richiesti per implementare un proxy di individuazione, un servizio individuabile che esegue la registrazione al proxy di individuazione e un client che utilizza il proxy di individuazione per trovare il servizio individuabile.</span><span class="sxs-lookup"><span data-stu-id="e9bad-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="e9bad-116">Controllo delle versioni per l'individuazione</span><span class="sxs-lookup"><span data-stu-id="e9bad-116">Discovery Versioning</span></span>](discovery-versioning.md)  
 <span data-ttu-id="e9bad-117">Fornisce una breve panoramica di un'implementazione del prototipo di alcune nuove funzionalità di individuazione.</span><span class="sxs-lookup"><span data-stu-id="e9bad-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="e9bad-118">Vengono inoltre forniti cenni preliminari sulla scelta della versione dell'individuazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e9bad-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="e9bad-119">Configurazione dell'individuazione in un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e9bad-119">Configuring Discovery in a Configuration File</span></span>](configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="e9bad-120">Mostra come configurare la funzionalità di individuazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="e9bad-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="e9bad-121">Utilizzo del canale client di individuazione</span><span class="sxs-lookup"><span data-stu-id="e9bad-121">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)  
 <span data-ttu-id="e9bad-122">Viene illustrato come utilizzare un canale del client di individuazione durante la scrittura di un'applicazione client WCF.</span><span class="sxs-lookup"><span data-stu-id="e9bad-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
