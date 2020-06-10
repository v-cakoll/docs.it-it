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
# <a name="wcf-discovery"></a>WCF Discovery
Windows Communication Foundation (WCF) fornisce il supporto per consentire ai servizi di essere individuabili in fase di esecuzione in modo interoperativo utilizzando il protocollo WS-Discovery. I servizi WCF possono annunciare la disponibilità alla rete utilizzando un messaggio multicast o a un server proxy di individuazione. Le applicazioni client possono eseguire ricerche nella rete o in un server proxy di individuazione per trovare servizi che soddisfano un set di criteri. Negli argomenti di questa sezione viene fornita una panoramica e viene proposta una descrizione dettagliata del modello di programmazione per questa funzionalità.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica di WCF Discovery](wcf-discovery-overview.md)  
 Viene fornita una panoramica del supporto WS-Discovery fornito da WCF.  
  
 [Modello a oggetti WCF Discovery](wcf-discovery-object-model.md)  
 Descrive le classi nel modello a oggetti e l'estensibilità del supporto WS-Discovery.  
  
 [Procedura: aggiungere capacità di individuazione a un client e un servizio WCF a livello di codice](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 Viene illustrato come rendere individuabile un servizio di Windows Communication Foundation (WCF).  
  
 [Implementazione di un proxy di individuazione](implementing-a-discovery-proxy.md)  
 Descrive i passaggi richiesti per implementare un proxy di individuazione, un servizio individuabile che esegue la registrazione al proxy di individuazione e un client che utilizza il proxy di individuazione per trovare il servizio individuabile.  
  
 [Controllo delle versioni per l'individuazione](discovery-versioning.md)  
 Fornisce una breve panoramica di un'implementazione del prototipo di alcune nuove funzionalità di individuazione. Vengono inoltre forniti cenni preliminari sulla scelta della versione dell'individuazione da usare.  
  
 [Configurazione dell'individuazione in un file di configurazione](configuring-discovery-in-a-configuration-file.md)  
 Mostra come configurare la funzionalità di individuazione nella configurazione.  
  
 [Utilizzo del canale client di individuazione](using-the-discovery-client-channel.md)  
 Viene illustrato come utilizzare un canale del client di individuazione durante la scrittura di un'applicazione client WCF.
