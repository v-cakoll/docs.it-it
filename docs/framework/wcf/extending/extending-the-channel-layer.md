---
title: Estensione del livello del canale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending channels [WCF]
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f9d14183092b70f0bbe1ce8894f10369aa46c31
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="extending-the-channel-layer"></a><span data-ttu-id="1e1b6-102">Estensione del livello del canale</span><span class="sxs-lookup"><span data-stu-id="1e1b6-102">Extending the Channel Layer</span></span>
<span data-ttu-id="1e1b6-103">Il livello del canale è responsabile dello scambio dei messaggi tra client e servizi.</span><span class="sxs-lookup"><span data-stu-id="1e1b6-103">The channel layer is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="1e1b6-104">Le estensioni del canale possono implementare nuove funzionalità del protocollo, ad esempio di sicurezza o di trasporto. Possono, ad esempio, implementare un nuovo trasporto di rete per il trasporto di messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="1e1b6-104">Channel extensions can implement new protocol functionality, such as security, or transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e1b6-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1e1b6-105">In This Section</span></span>  
 [<span data-ttu-id="1e1b6-106">Cenni preliminari sul modello di canale</span><span class="sxs-lookup"><span data-stu-id="1e1b6-106">Channel Model Overview</span></span>](../../../../docs/framework/wcf/extending/channel-model-overview.md)  
 <span data-ttu-id="1e1b6-107">Offre una panoramica dettagliata dei canali, delle funzionalità da essi fornite e del loro funzionamento in un'applicazione sia di servizio che client.</span><span class="sxs-lookup"><span data-stu-id="1e1b6-107">Provides a high-level overview of what channels are, the features that they provide and how they work both in a service and a client application.</span></span>  
  
 [<span data-ttu-id="1e1b6-108">Sviluppo di canali</span><span class="sxs-lookup"><span data-stu-id="1e1b6-108">Developing Channels</span></span>](../../../../docs/framework/wcf/extending/developing-channels.md)  
 <span data-ttu-id="1e1b6-109">Descrive dettagliatamente i ruoli svolti dai vari tipi di infrastruttura del canale, il funzionamento del motore di stato e del ciclo di vita dello stato, la gestione di eccezioni ed errori, l'implementazione del supporto dei metadati e il funzionamento dei canali con i codificatori di messaggi.</span><span class="sxs-lookup"><span data-stu-id="1e1b6-109">Describes in depth the roles that the various channel infrastructure types play, how the state engine and state lifecycle works, how to handle exceptions and faults, how to implement metadata support, and how channels work with message encoders.</span></span>  
  
 [<span data-ttu-id="1e1b6-110">Codificatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="1e1b6-110">Custom Encoders</span></span>](../../../../docs/framework/wcf/extending/custom-encoders.md)  
 <span data-ttu-id="1e1b6-111">Descrive il ruolo svolto dai codificatori di messaggi nei canali e la procedura per generarli.</span><span class="sxs-lookup"><span data-stu-id="1e1b6-111">Describes the role that message encoders play in channels and how to build one.</span></span>  
  
 [<span data-ttu-id="1e1b6-112">Aggiornamenti flusso personalizzati</span><span class="sxs-lookup"><span data-stu-id="1e1b6-112">Custom Stream Upgrades</span></span>](../../../../docs/framework/wcf/extending/custom-stream-upgrades.md)  
 <span data-ttu-id="1e1b6-113">Descrive il processo di aggiornamento dei flussi forniti da trasporti orientati al flusso.</span><span class="sxs-lookup"><span data-stu-id="1e1b6-113">Describes the process of upgrading the streams provided by stream-oriented transports.</span></span>
