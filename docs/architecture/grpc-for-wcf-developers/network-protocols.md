---
title: Protocolli di rete-gRPC per sviluppatori WCF
description: Panoramica dei protocolli di rete gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 1ceb140f7b7ac7e796a87612ebb9d21e28d33968
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628488"
---
# <a name="network-protocols"></a>Protocolli di rete

A differenza di Windows Communication Foundation (WCF), gRPC Usa HTTP/2 come base per la rete. Ciò offre vantaggi significativi rispetto a WCF e SOAP, che operano solo su HTTP/1.1. Per gli sviluppatori che vogliono usare gRPC, dato che non esiste alcuna alternativa a HTTP/2, sembrerebbe il momento ideale per esplorare HTTP/2 in modo più dettagliato e identificare i vantaggi aggiuntivi dell'uso di gRPC.

HTTP/2, rilasciato da Internet Engineering Task Force in 2015, è stato derivato dal protocollo sperimentale SPDY, che era già usato da Google. È stato progettato appositamente per essere più efficiente, più veloce e più sicuro rispetto a HTTP/1.1.

## <a name="key-features-of-http2"></a>Funzionalità principali di HTTP/2

In questo elenco vengono illustrate alcune delle principali funzionalità e vantaggi di HTTP/2:

### <a name="binary-protocol"></a>Protocollo binario

I cicli di richiesta/risposta non necessitano più di comandi di testo. Questo semplifica e velocizza l'implementazione dei comandi. In particolare, l'analisi dei dati è più veloce e usa meno memoria, la latenza di rete è ridotta con evidenti miglioramenti correlati alla velocità e c'è un uso ottimale delle risorse di rete.

### <a name="streams"></a>Flussi

I flussi consentono di creare connessioni di lunga durata tra mittente e ricevitore, in cui è possibile inviare più messaggi o frame in modo asincrono. Più flussi possono funzionare in modo indipendente su una singola connessione HTTP/2.

### <a name="request-multiplexing-over-a-single-tcp-connection"></a>Richiedi multiplexing su una singola connessione TCP

Questa funzionalità è una delle innovazioni più importanti di HTTP/2. Poiché consente più richieste parallele di dati, è ora possibile scaricare i file Web contemporaneamente da un singolo server. I siti Web vengono caricati più velocemente e la necessità di ottimizzazione è ridotta. Blocco Head-of-line (HOL), in cui le risposte pronte devono attendere l'invio finché non viene completata una richiesta precedente, viene anche attenuato (anche se il blocco di HOL può ancora verificarsi a livello di trasporto TCP).

### <a name="nettcp-like-performance-cross-platform"></a>Prestazioni di tipo NET. TCP, multipiattaforma

Fondamentalmente, la combinazione di gRPC e HTTP/2 offre agli sviluppatori almeno la velocità e l'efficienza equivalenti dei binding net. TCP per WCF e, in alcuni casi, una velocità ed efficienza ancora maggiore. Tuttavia, a differenza di NET. TCP, gRPC su HTTP/2 non è vincolato alle applicazioni .NET.

>[!div class="step-by-step"]
>[Precedente](interface-definition-language.md)
>[Successivo](why-grpc.md)
