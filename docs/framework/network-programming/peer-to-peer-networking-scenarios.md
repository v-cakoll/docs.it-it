---
title: Scenari di rete peer-to-peer
ms.date: 03/30/2017
ms.assetid: d23b1a64-2e08-4014-882a-c1dd766bdcc2
ms.openlocfilehash: 9b5d4d35085585fe04f2f0c0a105e6dff4b1fcc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "64623077"
---
# <a name="peer-to-peer-networking-scenarios"></a>Scenari di rete peer-to-peer

Una rete peer-to-peer supporta o ottimizza gli scenari seguenti:

## <a name="real-time-communications-rtc"></a>Comunicazioni in tempo reale

- Messaggistica immediata senza server

  Le comunicazioni in tempo reale sono già una realtà. Gli utenti di computer possono comunicare via chat e intrattenere conversazioni vocali o video con altri utenti. Tuttavia, molti dei programmi esistenti e dei relativi protocolli di comunicazione si basano sui server per funzionare. Se si partecipa a una rete wireless ad hoc o si fa parte di una rete isolata, non è possibile usare queste funzionalità di comunicazione in tempo reale. La tecnologia peer-to-peer consente l'estensione delle tecnologie di comunicazione in tempo reale a questi ambienti di rete aggiuntivi.

- Matchmaking e gioco in tempo reale

  Come le comunicazioni in tempo reale, oggi è già disponibile anche la possibilità di giocare con altri in tempo reale. Esistono molti siti di gioco basati sul Web che riuniscono la community dei giocatori tramite Internet e offrono la possibilità di trovare gli altri giocatori con interessi simili e giocare insieme. Il problema è che i siti di giochi sono disponibili solo in Internet e sono rivolti ai giocatori appassionati che amano mettersi alla prova con i migliori giocatori nel mondo. Questi siti tengono traccia di dati statistici e li mettono a disposizione per agevolare questo processo. Questi siti non consentono però a un giocatore di configurare un gioco ad hoc tra amici in svariati ambienti di rete. Una rete peer-to-peer può offrire questa funzionalità.

## <a name="collaboration"></a>Collaborazione

- Aree di lavoro per singoli progetti con obiettivi specifici

  Le applicazioni per aree di lavoro condivise consentono di creare gruppi di lavoro ad hoc e quindi consentono ai proprietari del gruppo di lavoro di popolare l'area di lavoro condivisa con gli strumenti e il contenuto che permetterà al gruppo di risolvere un problema. Può trattarsi di bacheche per messaggi, strumenti di produttività e file.

- Condivisione di file con altri utenti

  Una funzionalità secondaria della condivisione di un'area di lavoro per un progetto è la possibilità di condividere file. Sebbene questa possibilità esista già con la versione corrente di Windows, può essere migliorata tramite una rete peer-to-peer per rendere il contenuto di file disponibile in un modo semplice e accessibile. La possibilità di accedere facilmente all'incredibile quantità di contenuti disponibili ai margini di Internet o in ambienti informatici ad hoc aumenta il valore delle reti di computer.

- Condivisione di esperienze

  Con la sempre maggiore diffusione della connettività wireless, le reti peer-to-peer consentono di essere online in un gruppo di peer e di condividere esperienze in tempo reale, ad esempio un tramonto, un concerto o una vacanza.

## <a name="content-distribution"></a>Distribuzione del contenuto

- SMS

  Una rete peer-to-peer può consentire la diffusione di informazioni basate su testo sotto forma di file o messaggi a un ampio gruppo di utenti. Un esempio è un elenco di notizie.

- Audio e video

  Le reti peer-to-peer possono anche supportare la distribuzione di informazioni audio o video a un ampio gruppo di utenti, ad esempio una riunione aziendale o un concerto. Per distribuire il contenuto, è necessario configurare server ad alta capacità per la raccolta e la distribuzione del carico a centinaia o migliaia di utenti. Con una rete peer-to-peer, solo un numero limitato di peer otterrebbe in effetti il contenuto dai server centralizzati. Questi peer distribuirebbero le informazioni ad altre persone che le invierebbero ad altri e così via. Il carico della distribuzione del contenuto viene distribuito ai peer nel cloud. Un peer che vuole ricevere il contenuto individua il peer di distribuzione più vicino e ottiene il contenuto da tale peer.

- Distribuzione degli aggiornamenti dei prodotti

  Una rete peer-to-peer può inoltre rappresentare un meccanismo efficiente per distribuire il software, ad esempio gli aggiornamenti dei prodotti (aggiornamenti della sicurezza e Service Pack). Un peer con una connessione a un server di distribuzione software può ottenere l'aggiornamento del prodotto e propagarlo agli altri membri del gruppo.

## <a name="distributed-processing"></a>Elaborazione distribuita

- Suddivisione e distribuzione di un'attività

  Un'attività di elaborazione estesa può essere suddivisa in attività più piccole distinte, adatte alle risorse di elaborazione di un peer. Un peer può occuparsi della suddivisione dell'attività di elaborazione estesa e quindi la rete peer-to-peer può distribuire le singole attività ai peer separati nel gruppo. Ogni peer esegue l'attività di elaborazione assegnata e restituisce il risultato a un punto di raccolta centralizzato.

- Aggregazione di risorse dei computer

  Un altro modo per utilizzare la rete peer-to-peer per l'elaborazione distribuita consiste nell'eseguire in ogni peer programmi eseguiti durante i periodi di inattività del processore e che fanno parte di un'attività di elaborazione più grande coordinata da un server centrale. Aggregando i processori di più computer, la rete peer-to-peer può trasformare un gruppo di computer peer in un grande processore parallelo per attività di elaborazione estese.

## <a name="see-also"></a>Vedere anche

- <xref:System.Net.PeerToPeer.Collaboration>
