---
title: Scenari relativi al canale peer
ms.date: 03/30/2017
ms.assetid: dae6e0f7-900c-45ee-8be9-3647698382fb
ms.openlocfilehash: c4c24a0bafa4f73760d02de6242a9ed438d7d60e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596877"
---
# <a name="peer-channel-scenarios"></a>Scenari relativi al canale peer
Le API del canale peer supportano gli scenari di sviluppo seguenti.  
  
## <a name="publicationsubscription-messaging"></a>Messaggistica di pubblicazione/sottoscrizione  
 Le aziende che creano applicazioni di pubblicazione/sottoscrizione, ad esempio quotazioni azionarie, applicazioni di pubblicazione di notizie, risultati sportivi e previsioni meteo, possono usare il canale peer per le applicazioni senza server. Gli utenti possono, ad esempio, ottenere gli ultimi punteggi sportivi unendosi a una mesh comune (o gruppo di client) e propagare la grande quantità di dati di gioco aggiornati senza aumentare il carico del server. Questo consente ai provider dei dati di assicurare una più alta qualità del servizio senza aumentare significativamente l'investimento in tecnologie basate su server.  
  
## <a name="collaboration"></a>Collaborazione  
 I fornitori di software indipendenti (ISV) possono creare applicazioni che consentano alle persone di creare gruppi ristretti per la partecipazione ad attività peer-to-peer. Sono inclusi, ad esempio, team che si occupano di progetti collaborativi, condividono foto, organizzano feste e così via. Benché queste attività implichino, in genere, l'uso di server, il canale peer consente di eseguirle a costi più contenuti offrendo scenari di accesso non in linea che non è possibile implementare altrettanto facilmente in un modello client-server tradizionale.  
  
## <a name="distributed-processing-and-compute-clusters"></a>Elaborazione distribuita e cluster di calcolo  
 I cluster di calcolo e l'elaborazione distribuita vengono in genere usati per i calcoli su vasta scala, previsti ad esempio dalla modellazione finanziaria/meteorologica e dalla decodifica del DNA umano. Di norma, per eseguire queste operazioni, i server assegnano singolarmente le attività a tutti i client che partecipano al cluster di calcolo. Questi server possono, inoltre, dover gestire requisiti aggiuntivi; può, ad esempio, essere necessario che tutte le attività vengano completate entro un determinato periodo di tempo, coinvolgendo più di un computer per ogni attività. Inoltre, se un client che esegue un'attività subisce un'interruzione, un altro client deve essere in grado di occuparsi di quell'attività ed eseguirla. Allo stesso modo, è possibile che più client debbano eseguire la stessa attività per assicurare risultati coerenti. Sebbene i server possano eseguire questo tipo di coordinamento dei client, è possibile creare una soluzione peer-to-peer in cui i client che ricevono un'attività determinano indipendentemente i requisiti server relativi all'attività e usano una mesh di calcolo per stabilire come completare l'attività in questione.  
  
## <a name="gaming"></a>Modalità di gioco  
 Con il canale peer, gli sviluppatori di applicazioni possono creare versioni senza server dei giochi, in cui i movimenti di gioco vengono trasmessi e sincronizzati con gli altri giocatori da un meccanismo peer-to-peer anziché da un server centrale. Per gli ISV di piccole dimensioni, questo consente di eliminare i costi operativi associati alla distribuzione, alla gestione e al supporto di server centrali. I giochi scritti usando un'architettura peer-to-peer possono essere riprodotti in Internet o in reti locali cablate o wireless. Le attività di gioco secondarie, quali la sala d'attesa e la chat, possono essere sviluppate usando una rete peer-to-peer.  
  
## <a name="see-also"></a>Vedere anche

- [Concetti relativi al canale peer](peer-channel-concepts.md)
