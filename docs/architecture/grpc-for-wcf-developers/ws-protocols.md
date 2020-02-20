---
title: Protocolli WS-*-gRPC per sviluppatori WCF
description: Esaminare i protocolli WS-* supportati da WCF e le alternative disponibili con gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: c8c06a5e23a4d7859165e1c562032055d63d76f7
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503291"
---
# <a name="ws--protocols"></a>Protocolli WS-\*

Uno dei vantaggi effettivi dell'utilizzo di Windows Communication Foundation (WCF) era che supportava molti dei protocolli standard _WS-\*_ esistenti. In questa sezione viene illustrato brevemente il modo in cui gRPC gestisce gli stessi protocolli WS-\* e illustra le opzioni disponibili quando non esiste alcuna alternativa.

## <a name="metadata-exchange-ws-policy-ws-discovery-and-so-on"></a>Scambio di metadati: WS-Policy, WS-Discovery e così via

I servizi SOAP espongono documenti di schema Web Services Description Language (WSDL) con informazioni quali formati di dati, operazioni o opzioni di comunicazione. È possibile utilizzare questo schema per generare il codice client.

gRPC funziona in modo ottimale quando i server e i client vengono generati dagli stessi file di `.proto`, ma un'estensione facoltativa di Reflection Server consente di esporre informazioni dinamiche da un server in esecuzione. Per altre informazioni, vedere il pacchetto NuGet [Grpc. Reflection](https://nuget.org/packages/Grpc.Reflection) e l' [articolo C# Reflection server Grpc](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) .

Il protocollo WS-Discovery viene utilizzato per individuare i servizi in una rete locale. i servizi gRPC si trovano in genere tramite DNS o un registro di sistema del servizio, ad esempio Consul o ZooKeeper.

## <a name="security-ws-security-ws-federation-xml-encryption-and-so-on"></a>Sicurezza: WS-Security, WS-Federation, crittografia XML e così via

Sicurezza, autenticazione e autorizzazione sono trattati in modo più dettagliato nel [capitolo 6](security.md). Tuttavia, è importante notare che, a differenza di WCF, gRPC non supporta WS-Security, WS-Federation o la crittografia XML. Anche in questo caso, gRPC offre una sicurezza eccellente. Tutto il traffico di rete gRPC viene crittografato automaticamente quando usa HTTP/2 su TLS. È possibile usare i certificati X509 per l'autenticazione reciproca tra client e server.

## <a name="ws-reliablemessaging"></a>WS-ReliableMessaging

gRPC non fornisce un equivalente a WS-ReliableMessaging. La semantica di ripetizione dei tentativi deve essere gestita nel codice, possibilmente con una libreria come [Polly](https://github.com/App-vNext/Polly). Quando si esegue in Kubernetes o in ambienti di orchestrazione simili, i [mesh](service-mesh.md) dei servizi consentono anche di fornire messaggistica affidabile tra i servizi.

## <a name="ws-transaction-ws-coordination"></a>WS-Transaction, WS-Coordination

L'implementazione di transazioni distribuite di WCF utilizza Microsoft Distributed Transaction Coordinator (MSDTC). Funziona con i gestori di risorse che lo supportano in modo specifico, ad esempio SQL Server, MSMQ o file System Windows. Non esiste ancora un equivalente nel mondo dei microservizi moderni, in parte grazie alla più ampia gamma di tecnologie in uso. Per informazioni sulle transazioni, vedere [appendice a](appendix.md).

>[!div class="step-by-step"]
>[Precedente](error-handling.md)
>[Successivo](migrate-wcf-to-grpc.md)
