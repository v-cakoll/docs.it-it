---
title: Panoramica di gRPC-gRPC per sviluppatori WCF
description: Informazioni sul set di principi che guidano lo sviluppo di gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: a92fe7ca2f8e17126025362fcc3c190024ebf7d3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967757"
---
# <a name="grpc-overview"></a>Panoramica di gRPC

Dopo aver esaminato la genesi di WCF e gRPC nell'ultimo capitolo, in questo capitolo verranno prese in considerazione alcune delle funzionalità principali di gRPC e il modo in cui vengono confrontate con WCF.

ASP.NET Core 3,0 è la prima versione di ASP.NET che supporta in modo nativo gRPC come un cittadino di prima classe, con i team Microsoft che contribuiscono all'implementazione di .NET ufficiale di gRPC. Si tratta di un approccio consigliato per la creazione di applicazioni distribuite con .NET in grado di interagire con tutti gli altri linguaggi e Framework di programmazione principali.

## <a name="key-principles"></a>Principi chiave

Come illustrato nel capitolo 1, Google ha voluto usare l'introduzione di HTTP/2 per sostituire Stubby, l'infrastruttura RPC per utilizzo generico interna. gRPC, basato su Stubby, ora può sfruttare i vantaggi della standardizzazione ed estendere la relativa applicabilità al mobile computing, al cloud e al Internet delle cose.

A tale scopo, il [cloud native Computing Foundation (CNCF)](https://www.cncf.io/) ha stabilito un set di principi che governano gRPC. Nell'elenco seguente sono illustrati i più rilevanti, che riguardano principalmente la massimizzazione dell'accessibilità e dell'usabilità:

- **Gratuito e aperto** : tutti gli elementi devono essere open source con licenze che non vincolano gli sviluppatori all'adozione di gRPC.
- **Code coverage e semplicità** : gRPC dovrebbe essere disponibile in tutte le piattaforme più diffuse e abbastanza semplice da creare su qualsiasi piattaforma.
- **Interoperabilità e REACH** : dovrebbe essere possibile usare gRPC in qualsiasi rete, indipendentemente dalla larghezza di banda o dalla latenza, usando gli standard di rete ampiamente disponibili.
- Utilizzo **generico ed efficiente** : il Framework deve essere utilizzabile in un'ampia gamma di casi d'uso possibili senza compromettere le prestazioni.
- **Streaming** : il protocollo deve fornire la semantica di flusso per set di dati di grandi dimensioni o messaggistica asincrona.
- **Scambio di metadati** : il protocollo consente ai dati non aziendali, ad esempio i token di autenticazione, di essere gestiti separatamente dai dati aziendali effettivi.
- **Codici di stato standardizzati** : la variabilità dei codici di errore deve essere ridotta per semplificare le decisioni di gestione degli errori e, in cui è necessaria una gestione degli errori più completa, è necessario fornire un meccanismo per gestirlo nello scambio di metadati.

>[!div class="step-by-step"]
>[Precedente](introduction.md)
>[Successivo](approach.md)
