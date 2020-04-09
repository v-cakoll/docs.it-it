---
title: Introduzione - gRPC per gli sviluppatori WCFIntroduction - gRPC for WCF developers
description: Introduzione
ms.date: 09/02/2019
ms.openlocfilehash: 41f470eb02a77b1b6a26a7d4c2ca347ad07d828d
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988934"
---
# <a name="introduction"></a>Introduzione

Aiutare le macchine a comunicare tra loro è stata una delle principali preoccupazioni dell'era digitale. In particolare, è in corso uno sforzo per determinare il meccanismo di comunicazione remota ottimale che soddisfi le esigenze di interoperabilità dell'infrastruttura corrente. Come potete immaginare, questo meccanismo cambia con l'evoluzione delle esigenze o dell'infrastruttura.

Il rilascio di .NET Core 3.0 segna un cambiamento nel modo in cui Microsoft offre soluzioni di comunicazione remota agli sviluppatori che desiderano fornire servizi su una vasta gamma di piattaforme. .NET Core non offre Windows Communication Foundation (WCF) predefinito ma, con il rilascio di ASP.NET Core 3.0, fornisce funzionalità gRPC incorporate.

gRPC è un framework popolare nella comunità di software più ampia. Viene utilizzato dagli sviluppatori in molti linguaggi di programmazione per gli scenari RPC moderni. La comunità e l'ecosistema sono vibranti e attivi. Il supporto per il protocollo gRPC viene aggiunto acomponenti dell'infrastruttura come Kubernetes, le maglie dei servizi, i servizi di bilanciamento del carico e altro ancora. Questi fattori, insieme alle prestazioni, all'efficienza e alla compatibilità multipiattaforma, rendono gRPC una scelta naturale per le nuove app e le app WCF che passano a .NET Core.

## <a name="history"></a>Cronologia

Il principio fondamentale di una rete di computer come nient'altro che un gruppo di computer che si scambiano dati tra loro per raggiungere una serie di compiti interconnessi non è cambiato dal suo inizio. Ma la complessità, la scala e le aspettative sono cresciute in modo esponenziale.  

Nel corso degli anni '90, l'accento è stato posto principalmente sul miglioramento delle reti interne che utilizzavano la stessa lingua e le stesse piattaforme. TCP/IP è diventato il gold standard per questo tipo di comunicazione.

L'attenzione si è presto spostata sul modo migliore per ottimizzare la comunicazione tra più piattaforme promuovendo un approccio indipendente dalla lingua. L'architettura orientata ai servizi (SOA) ha fornito una struttura per l'accoppiamento di un'ampia raccolta di servizi che potrebbero essere forniti a un'applicazione.

Lo sviluppo dei *servizi web* si è verificato quando tutte le principali piattaforme potevano accedere a Internet, ma non potevano ancora interagire tra loro. I servizi Web dispongono di standard e protocolli aperti, tra cui:

- XML per contrassegnare e codificare i dati.
- Protocollo SOAP (Simple Object Access Protocol) per trasferire i dati.
- WSDL (Web Services Definition Language) per descrivere e connettere i servizi Web alle applicazioni client.
- UDDI (Universal Description, Discovery, and Integration) per rendere i servizi Web individuabili da altri servizi.

SOAP definisce le regole in base alle quali gli elementi distribuiti di un'applicazione possono comunicare tra loro, anche se si trovano su piattaforme diverse. SOAP è basato su XML, pertanto è leggibile. Il sacrificio per rendere SOAP facilmente comprensibile è la dimensione; I messaggi SOAP sono più grandi dei messaggi in protocolli comparabili. SOAP è stato progettato per suddividere le applicazioni monolitiche in forma multicomponente senza perdere sicurezza o controllo. Così WCF è stato progettato per funzionare con quel tipo di sistema, a differenza di gRPC, che ha iniziato come un sistema distribuito. WCF ha affrontato alcune di queste limitazioni sviluppando e documentando protocolli di estensione proprietari per lo stack SOAP, ma a costo di una mancanza di supporto da parte di altre piattaforme.

Windows Communication Foundation è un framework per la creazione di servizi. È stato progettato nei primi anni 2000 per aiutare gli sviluppatori che utilizzano il prime SOA a gestire le complessità di lavoro con SOAP. Anche se elimina la necessità per gli sviluppatori di scrivere i propri protocolli SOAP, WCF utilizza ancora SOAP per consentire l'interoperabilità con altri sistemi. WCF è stato inoltre progettato per fornire soluzioni su più protocolli (HTTP/1.1, Net.TCP e così via).

## <a name="microservices"></a>Microservizi

Nelle architetture di microservizi, le applicazioni di grandi dimensioni vengono create come una raccolta di servizi modulari più piccoli. Ogni componente esegue un'attività o un processo specifico e i componenti sono progettati per funzionare in modo interoperabile, ma possono essere isolati in base alle esigenze.

I vantaggi per i microservizi includono:

- Le modifiche e gli aggiornamenti possono essere gestiti in modo indipendente.
- La gestione degli errori diventa più efficiente perché i problemi possono essere tracciati a servizi specifici che vengono quindi isolati, ricompilati, testati e ridistribuiti indipendentemente dagli altri servizi.
- La scalabilità può essere limitata a istanze o servizi specifici anziché all'intera applicazione.
- Lo sviluppo può avvenire tra più team, con meno attrito rispetto a quando molti team lavorano su una singola codebase.

Il passaggio all'aumento della virtualizzazione, del cloud computing, dei contenitori e dell'Internet of Things ha contribuito alla continua crescita dei microservizi. Ma i microservizi non sono privi di sfide. L'infrastruttura frammentata/decentralizzata pone maggiormente l'accento sulla necessità di semplicità e velocità nella comunicazione tra i servizi. Questo a sua volta attirò l'attenzione sulla natura a volte laboriosa e contorta del SOAP.

E 'stato in questo ambiente che gRPC è stato lanciato, 10 anni dopo Che Microsoft ha rilasciato WCF. Evoluto direttamente dall'infrastruttura interna di Google RPC (Stubby), gRPC non è mai stato basato sugli stessi standard e protocolli che avevano informato i parametri di molte RPC precedenti. E gRPC è stato sempre solo basato su HTTP/2. Ecco perché potrebbe attingere alle nuove funzionalità fornite dal protocollo di trasporto avanzato. In particolare, streaming bidirezionale, messaggistica binaria e multiplexing.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida illustra le caratteristiche principali di gRPC. I primi capitoli prendono un'occhiata di alto livello alle principali caratteristiche di WCF e confrontarli con quelli di gRPC. Identifica dove ci sono correlazioni dirette tra WCF e gRPC e anche dove gRPC offre un vantaggio. Quando non esiste alcuna correlazione tra WCF e gRPC, o quando gRPC non è in grado di offrire una soluzione equivalente a WCF, questa guida suggerirà soluzioni alternative o dove andare per ulteriori informazioni.

Utilizzando un set di applicazioni WCF di esempio, capitolo 5 è uno sguardo approfondito per la conversione dei principali tipi di servizio WCF (semplice richiesta-risposta, unidirezionale e streaming) ai loro equivalenti in gRPC.

La sezione finale del libro esamina come ottenere il meglio da gRPC in pratica. Questa sezione include informazioni sull'utilizzo di strumenti aggiuntivi, come contenitori Docker o Kubernetes, per sfruttare l'efficienza di gRPC. Include inoltre un'analisi dettagliata del monitoraggio con la registrazione, le metriche e la traccia distribuita.

## <a name="who-this-guide-is-for"></a>A chi è destinata questa guida

Questa guida è stata scritta per gli sviluppatori che lavorano in .NET Framework o .NET Core che hanno utilizzato WCF e che stanno cercando di eseguire la migrazione delle applicazioni in un ambiente RPC moderno per .NET Core 3.0 e versioni successive. La guida potrebbe anche essere utile più in generale per gli sviluppatori l'aggiornamento o la considerazione di aggiornamento a .NET Core 3.0 e che desiderano utilizzare gli strumenti gRPC incorporati.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](grpc-overview.md)
