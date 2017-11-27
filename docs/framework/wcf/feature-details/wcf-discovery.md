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
# <a name="wcf-discovery"></a>WCF Discovery
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] fornisce il supporto per l'individuabilità dei servizi in fase di esecuzione in una modalità interoperativa utilizzando il protocollo WS-Discovery. I servizi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono annunciare la disponibilità alla rete utilizzando un messaggio multicast o a un server proxy di individuazione. Le applicazioni client possono eseguire ricerche nella rete o in un server proxy di individuazione per trovare servizi che soddisfano un set di criteri. Negli argomenti di questa sezione viene fornita una panoramica e viene proposta una descrizione dettagliata del modello di programmazione per questa funzionalità.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica di WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 Fornisce una panoramica del supporto WS-Discovery fornito da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Modello a oggetti WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 Descrive le classi nel modello a oggetti e l'estensibilità del supporto WS-Discovery.  
  
 [Procedura: aggiungere a livello di programmazione esposizione al rilevamento a un servizio WCF e un Client](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 Mostra come rendere individuabile un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 [Implementazione di un Proxy di individuazione](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 Descrive i passaggi richiesti per implementare un proxy di individuazione, un servizio individuabile che esegue la registrazione al proxy di individuazione e un client che utilizza il proxy di individuazione per trovare il servizio individuabile.  
  
 [Controllo delle versioni di individuazione](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 Fornisce una breve panoramica di un'implementazione del prototipo di alcune nuove funzionalità di individuazione. Vengono inoltre forniti cenni preliminari sulla scelta della versione dell'individuazione da usare.  
  
 [Configurazione dell'individuazione in un File di configurazione](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 Mostra come configurare la funzionalità di individuazione nella configurazione.  
  
 [Utilizzo del canale Client di individuazione](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 Mostra come utilizzare un canale client di individuazione in caso di scrittura di un'applicazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].
