---
title: Introduzione-gRPC per sviluppatori WCF
description: Introduzione
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 9eb12d5060ddf4f345ebe095738c98238c6caab7
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846631"
---
# <a name="introduction"></a>Introduzione

Aiutare i computer a comunicare tra loro è stato uno dei principali preoccupati della validità digitale. In particolare, è possibile determinare il meccanismo di comunicazione remota ottimale che soddisferà le richieste di interoperabilità dell'infrastruttura corrente. Come si può immaginare, questo meccanismo cambia come le richieste o l'infrastruttura si evolve.

Il rilascio di .NET Core 3,0 segna un cambiamento nel modo in cui Microsoft offre soluzioni di comunicazione remota per gli sviluppatori che desiderano distribuire servizi in un'ampia gamma di piattaforme. .NET Core non offre Windows Communication Foundation (WCF), ma con il rilascio della versione ASP.NET Core 3,0, fornisce funzionalità gRPC predefinite.

gRPC è un Framework comune nella community software più ampia, usato dagli sviluppatori in molti linguaggi di programmazione per gli scenari RPC moderni. La community e l'ecosistema sono vivaci e attive, grazie al supporto per il protocollo gRPC aggiunto ai componenti dell'infrastruttura, come Kubernetes, mesh del servizio, servizi di bilanciamento del carico e altro ancora. Questi fattori, così come le prestazioni, l'efficienza e la compatibilità multipiattaforma, rendono gRPC una scelta naturale per le nuove app e le app WCF che passano a .NET Core.

## <a name="history"></a>Cronologia

Il principio fondamentale di una rete di computer non è cambiato rispetto a un gruppo di computer che scambiano dati tra loro per ottenere un set di attività correlate. Tuttavia, la complessità, la scalabilità e le aspettative sono aumentate esponenzialmente.  

Negli anni '90, l'enfasi si è concentrata principalmente sul miglioramento delle reti interne con lo stesso linguaggio e le stesse piattaforme. TCP/IP è diventato lo standard Gold per questo tipo di comunicazione.

Tuttavia, lo stato attivo si è subito trasferito al modo migliore per ottimizzare la comunicazione tra più piattaforme, innalzando di livello un approccio indipendente dal linguaggio. L'architettura orientata ai servizi (SOA) fornisce una struttura per l'accoppiamento libero di un'ampia raccolta di servizi che possono essere forniti a un'applicazione.

Lo sviluppo dei *servizi Web* si è verificato quando tutte le piattaforme principali potevano accedere a Internet, ma non potevano interagire tra loro. I servizi Web dispongono di standard e protocolli aperti, tra cui:

- XML per contrassegnare e codificare i dati;
- Simple Object Access Protocol (SOAP) per il trasferimento dei dati;
- WSDL (Web Services Definition Language): descrive e connette il servizio Web all'applicazione client. *e*
- UDDI (Universal Description Discovery Integration): consente ai servizi Web di essere individuabili da altri servizi

SOAP definisce le regole in base alle quali gli elementi distribuiti di un'applicazione possono comunicare tra loro anche se si trovano su piattaforme diverse. SOAP si basa su XML, quindi è leggibile. Il sacrificio per rendere SOAP facilmente comprensibile è la dimensione; I messaggi SOAP sono più grandi dei messaggi nei protocolli confrontabili. SOAP è stato progettato per suddividere le applicazioni monolitiche in form multicomponente senza perdere sicurezza o controllo. Pertanto, WCF è stato progettato per funzionare con tale tipo di sistema, a differenza di gRPC, che inizia come sistema distribuito. WCF ha risolto alcune di queste limitazioni sviluppando e documentando protocolli di estensione proprietari per lo stack SOAP, ma con il costo della mancanza di supporto da altre piattaforme.

Windows Communication Foundation è un Framework per la creazione di servizi. Il servizio è stato progettato nel primo millennio per aiutare gli sviluppatori a usare i primi SOA per gestire le complessità dell'utilizzo di SOAP. Sebbene rimuova la necessità per lo sviluppatore di scrivere i propri protocolli SOAP, WCF usa ancora SOAP per consentire l'interoperabilità con altri sistemi. WCF è stato inoltre progettato per fornire soluzioni su più protocolli (HTTP/1.1, NetTCP e così via).

## <a name="microservices"></a>Microservizi

Nelle architetture di microservizi, le applicazioni di grandi dimensioni sono compilate come una raccolta di servizi modulari di dimensioni ridotte. Ogni componente esegue un'attività o un processo specifico e i componenti sono progettati per funzionare in modo interoperativo, ma possono essere isolati se necessario.

I vantaggi offerti dai microservizi sono i seguenti:

- Le modifiche e gli aggiornamenti possono essere gestiti in modo indipendente.
- La gestione degli errori diventa più efficiente perché i problemi possono essere tracciati in servizi specifici che vengono quindi isolati, ricompilati, testati e ridistribuiti indipendentemente dagli altri servizi.
- È possibile limitare la scalabilità alle istanze o ai servizi specifici anziché all'intera applicazione.
- Lo sviluppo può avvenire tra più team, con minore attrito rispetto a quando molti team lavorano su una singola codebase.

Il passaggio verso l'aumento della virtualizzazione, cloud computing, i contenitori e i Internet delle cose hanno contribuito all'incremento continuo dei microservizi. I microservizi, tuttavia, non sono privi di problemi. L'infrastruttura frammentata/decentralizzata pone più enfasi sulla necessità della semplicità e della velocità durante la comunicazione tra i servizi. Questo ha a sua volta attirato l'attenzione sulla natura a volte laboriosa e contorta di SOAP.

In questo ambiente è stato avviato gRPC, 10 anni dopo il rilascio di WCF da Microsoft. Si è evoluto direttamente dall'infrastruttura RPC (Stubby) interna di Google, gRPC non era mai basato sugli stessi standard e protocolli che informavano i parametri di molte RPC precedenti. Inoltre, gRPC è stato basato solo su HTTP/2 ed è per questo motivo che è possibile creare sulle nuove funzionalità fornite dal protocollo di trasporto avanzato. In particolare, streaming bidirezionale, messaggistica binaria e multiplexing.

## <a name="about-this-guide"></a>Informazioni sulla guida

Questa guida descrive le funzionalità chiave di gRPC. I primi capitoli esaminano in modo dettagliato le funzionalità principali di WCF e le confrontano con gRPC. Identifica la posizione in cui si trovano le correlazioni dirette tra WCF e gRPC e anche in cui gRPC offre un vantaggio. In assenza di correlazioni tra WCF e gRPC o in cui gRPC non è in grado di offrire una soluzione equivalente a WCF, in questa guida verranno suggerite le soluzioni alternative o i punti da usare per ulteriori informazioni.

Utilizzando un set di applicazioni WCF di esempio, il capitolo 5 è un approfondimento sulla conversione dei tipi principali di servizio WCF (semplice richiesta-risposta, unidirezionale e streaming) negli equivalenti in gRPC.

La sezione finale del libro esamina come ottenere il meglio da gRPC, tra cui l'uso di strumenti aggiuntivi come i contenitori Docker o Kubernetes per sfruttare l'efficienza di gRPC e un esame dettagliato del monitoraggio con registrazione, metriche e Distributed traccia.

## <a name="whom-this-guide-is-for"></a>Destinatari della Guida

Questa guida è stata scritta per gli sviluppatori che lavorano in .NET Framework o .NET Core che hanno usato in precedenza WCF e che stanno tentando di eseguire la migrazione delle applicazioni a un ambiente RPC moderno per .NET Core 3,0 e versioni successive. La guida può anche essere usata più in generale per gli sviluppatori che eseguono l'aggiornamento o l'aggiornamento a .NET Core 3,0 che vogliono usare gli strumenti gRPC predefiniti.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](grpc-overview.md)
