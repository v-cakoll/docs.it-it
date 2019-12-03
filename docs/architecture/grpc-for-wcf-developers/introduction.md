---
title: Introduzione-gRPC per sviluppatori WCF
description: Introduzione
ms.date: 09/02/2019
ms.openlocfilehash: 2f36d6294e2c76309b051fb3af21157cbfc1087a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711241"
---
# <a name="introduction"></a>Introduzione

Aiutare i computer a comunicare tra loro è stato uno dei principali preoccupati della validità digitale. In particolare, è possibile determinare il meccanismo di comunicazione remota ottimale che soddisferà le richieste di interoperabilità dell'infrastruttura corrente. Come si può immaginare, questo meccanismo cambia come le richieste o l'infrastruttura si evolve.

Il rilascio di .NET Core 3,0 segna un cambiamento nel modo in cui Microsoft offre soluzioni di comunicazione remota per gli sviluppatori che desiderano distribuire servizi in un'ampia gamma di piattaforme. .NET Core non offre Windows Communication Foundation (WCF), ma con il rilascio di ASP.NET Core 3,0, fornisce funzionalità gRPC predefinite.

gRPC è un Framework comune nella community software più ampia. Viene usato dagli sviluppatori in molti linguaggi di programmazione per gli scenari RPC moderni. La community e l'ecosistema sono vivaci e attive. È in corso l'aggiunta del supporto per il protocollo gRPC ai componenti dell'infrastruttura, come Kubernetes, mesh del servizio, servizi di bilanciamento del carico e altro ancora. Questi fattori, insieme alle relative prestazioni, efficienza e compatibilità multipiattaforma, rendono gRPC una scelta naturale per le nuove app e le app WCF che passano a .NET Core.

## <a name="history"></a>Cronologia

Il principio fondamentale di una rete di computer non è cambiato rispetto a un gruppo di computer che scambiano dati tra loro per ottenere un set di attività correlate. Tuttavia, la complessità, la scalabilità e le aspettative sono aumentate esponenzialmente.  

Negli anni '90, l'enfasi è stata soprattutto sul miglioramento delle reti interne che usavano lo stesso linguaggio e le stesse piattaforme. TCP/IP è diventato lo standard Gold per questo tipo di comunicazione.

Lo stato attivo si è subito trasferito al modo migliore per ottimizzare la comunicazione tra più piattaforme, favorendo un approccio indipendente dal linguaggio. L'architettura orientata ai servizi (SOA) fornisce una struttura per l'accoppiamento libero di un'ampia raccolta di servizi che possono essere forniti a un'applicazione.

Lo sviluppo dei *servizi Web* si è verificato quando tutte le piattaforme principali potevano accedere a Internet, ma non potevano interagire tra loro. I servizi Web dispongono di standard e protocolli aperti, tra cui:

- XML per contrassegnare e codificare i dati.
- Simple Object Access Protocol (SOAP) per trasferire i dati.
- WSDL (Web Services Definition Language) per descrivere e connettere i servizi Web alle applicazioni client.
- Universal Description, Discovery, and Integration (UDDI) per rendere i servizi Web individuabili da altri servizi.

SOAP definisce le regole in base alle quali gli elementi distribuiti di un'applicazione possono comunicare tra loro, anche se si trovano su piattaforme diverse. SOAP si basa su XML, quindi è leggibile. Il sacrificio per rendere SOAP facilmente comprensibile è la dimensione; I messaggi SOAP sono più grandi dei messaggi nei protocolli confrontabili. SOAP è stato progettato per suddividere le applicazioni monolitiche in moduli multicomponente senza perdere sicurezza o controllo. Quindi, WCF è stato progettato per funzionare con questo tipo di sistema, a differenza di gRPC, che inizia come sistema distribuito. WCF ha risolto alcune di queste limitazioni sviluppando e documentando protocolli di estensione proprietari per lo stack SOAP, ma a scapito della mancanza di supporto da altre piattaforme.

Windows Communication Foundation è un Framework per la creazione di servizi. Il servizio è stato progettato nel primo millennio per aiutare gli sviluppatori a usare i primi SOA per gestire le complessità dell'utilizzo di SOAP. Sebbene rimuova il requisito per gli sviluppatori di scrivere i propri protocolli SOAP, WCF usa ancora SOAP per consentire l'interoperabilità con altri sistemi. WCF è stato inoltre progettato per fornire soluzioni su più protocolli (HTTP/1.1, NET. TCP e così via).

## <a name="microservices"></a>Microservizi

Nelle architetture di microservizi, le applicazioni di grandi dimensioni sono compilate come una raccolta di servizi modulari di dimensioni ridotte. Ogni componente esegue un'attività o un processo specifico e i componenti sono progettati per funzionare in modo interoperativo, ma possono essere isolati se necessario.

I vantaggi offerti dai microservizi sono i seguenti:

- Le modifiche e gli aggiornamenti possono essere gestiti in modo indipendente.
- La gestione degli errori diventa più efficiente perché è possibile tracciare problemi a servizi specifici che vengono quindi isolati, ricompilati, testati e ridistribuiti in modo indipendente dagli altri servizi.
- È possibile limitare la scalabilità a istanze o servizi specifici anziché all'intera applicazione.
- Lo sviluppo può avvenire tra più team, con minore attrito rispetto a quando molti team lavorano su una singola codebase.

Il passaggio verso l'aumento della virtualizzazione, cloud computing, dei contenitori e della Internet delle cose ha contribuito all'incremento continuo dei microservizi. I microservizi, tuttavia, non sono privi di problemi. L'infrastruttura frammentata/decentralizzata pone maggiori enfasi sulla necessità di semplicità e velocità durante la comunicazione tra i servizi. Questo ha a sua volta attirato l'attenzione sulla natura a volte laboriosa e contorta di SOAP.

In questo ambiente è stato avviato gRPC, 10 anni dopo il rilascio di WCF da Microsoft. Si è evoluto direttamente dall'infrastruttura RPC (Stubby) interna di Google, gRPC non era mai basato sugli stessi standard e protocolli che informavano i parametri di molte RPC precedenti. E gRPC è stato sempre basato solo su HTTP/2. Questo è il motivo per cui è possibile basare sulle nuove funzionalità fornite dal protocollo di trasporto avanzato. In particolare, streaming bidirezionale, messaggistica binaria e multiplexing.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida descrive le funzionalità chiave di gRPC. I primi capitoli prevedono una panoramica delle principali funzionalità di WCF e la loro confronto con quelle di gRPC. Identifica la posizione in cui sono presenti correlazioni dirette tra WCF e gRPC e anche in cui gRPC offre un vantaggio. Quando non è presente alcuna correlazione tra WCF e gRPC o quando gRPC non è in grado di offrire una soluzione equivalente a WCF, in questa guida verranno suggerite le soluzioni alternative o la posizione per ulteriori informazioni.

Grazie a un set di applicazioni WCF di esempio, il capitolo 5 è una procedura approfondita per la conversione dei tipi principali di servizio WCF (semplice richiesta-risposta, unidirezionale e flusso) negli equivalenti in gRPC.

La sezione finale del libro esamina come ottenere il meglio da gRPC in pratica. Questa sezione include informazioni sull'uso di strumenti aggiuntivi, come i contenitori Docker o Kubernetes, per sfruttare i vantaggi offerti dall'efficienza di gRPC. Include anche un'analisi dettagliata del monitoraggio con la registrazione, le metriche e la traccia distribuita.

## <a name="who-this-guide-is-for"></a>A chi è destinata questa guida

Questa guida è stata scritta per gli sviluppatori che lavorano in .NET Framework o .NET Core che hanno usato WCF e che stanno tentando di eseguire la migrazione delle applicazioni a un ambiente RPC moderno per .NET Core 3,0 e versioni successive. La guida potrebbe anche essere utile più in generale per gli sviluppatori che aggiornano o valutano l'aggiornamento a .NET Core 3,0 e che vogliono usare gli strumenti gRPC predefiniti.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](grpc-overview.md)
