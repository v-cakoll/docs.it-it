---
title: REST e gRPC
description: Informazioni su gRPC, il suo ruolo in applicazioni native del cloud e su come differisce da HTTP REST
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: c77343e7a594d34cbd2c00ce11281bd6bf4000c1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337066"
---
# <a name="rest-and-grpc"></a>REST e gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Fino a questo libro abbiamo incentrato sulla comunicazione [basata su REST](https://docs.microsoft.com/azure/architecture/best-practices/api-design) . REST è uno stile di architettura che promuove l'interoperabilità tra i sistemi di computer distribuiti. Usa un modello di richiesta/risposta in cui ogni risposta dal server corrisponde a una richiesta del client. Sebbene sia molto diffuso, REST non è la soluzione ideale per ogni problema. Una tecnologia di comunicazione più recente, intitolata gRPC, sta ottenendo rapidamente popolarità ed è in grado di raggiungere il mondo nativo del cloud.

## <a name="grpc"></a>gRPC

gRPC è una comunicazione Open Source originata da Google. Si basa sul modello [RPC (Remote Procedure Call)](https://en.wikipedia.org/wiki/Remote_procedure_call) , più diffuso nell'elaborazione distribuita. Seguendo questo modello, un programma client locale espone un metodo in-process per eseguire un'operazione. Dietro le quinte, la chiamata viene richiamata su un microservizio out-of-process in una rete distribuita. Lo sviluppatore codifica l'operazione come chiamata di procedura locale. La piattaforma sottostante astrae le comunicazioni di rete, la serializzazione e l'esecuzione da punto a punto.

gRPC è un Framework RPC moderno che è leggero ed efficiente. Usa HTTP/2 per il relativo protocollo di trasporto. Sebbene compatibile con HTTP 1,1, HTTP/2 presenta numerose funzionalità avanzate:

- Quando HTTP 1,1 invia dati come testo non crittografato, HTTP/2 è un protocollo binario. Analizza i dati più velocemente usando meno memoria, riduce la latenza di rete con i miglioramenti correlati alla velocità e gestisce più efficacemente le risorse di rete.
- Sebbene HTTP 1,1 sia limitato all'elaborazione di una richiesta/risposta di round trip alla volta, HTTP/2 supporta il multiplexing o più richieste parallele sulla stessa connessione.
- HTTP/2 supporta la comunicazione full-duplex o bidirezionale, in cui sia il client che il server e possono comunicare allo stesso tempo. Il client può caricare i dati della richiesta nello stesso momento in cui il server invia i dati di risposta.
- Il flusso è integrato in HTTP/2, pertanto le richieste e le risposte possono trasmettere in modo asincrono set di dati di grandi dimensioni.
- La combinazione di gRPC e HTTP/2 comporta un aumento significativo delle prestazioni. Nel gergo [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) , le prestazioni di gRPC soddisfano e superano la velocità e l'efficienza delle [associazioni NetTcp](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8). Tuttavia, a differenza di NetTCP, gRPC non è vincolato a linguaggi Microsoft, C# ad esempio o Visual Basic.

gRPC è supportato nelle piattaforme più diffuse, tra cui Java C#,, Golang e NodeJS.

## <a name="protocol-buffers"></a>Buffer di protocollo

gRPC abbraccia un'altra tecnologia open source denominata [buffer del protocollo](https://developers.google.com/protocol-buffers/docs/overview) o messaggi protobuf per inviare e ricevere dati. Analogamente a un [contratto dati WCF](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-data-contracts), protobuf serializza i dati strutturati per i sistemi per la lettura e la scrittura. Riduce il sovraccarico dei formati leggibili come XML o JSON.

Molte tecniche di serializzazione degli oggetti riflettono la struttura degli oggetti dati in fase di esecuzione. Protobuf richiede di definire la struttura in primo piano con un linguaggio indipendente dalla piattaforma (linguaggio del buffer del protocollo). Ogni definizione viene archiviata in un file ". proto". Quindi, usando il compilatore protobuf, "Proton", viene generato il codice client e server per qualsiasi piattaforma supportata. Il codice generato è ottimizzato per la serializzazione/deserializzazione rapida dei dati. In fase di esecuzione, ogni messaggio viene incluso nel contratto di servizio fortemente tipizzato e serializzato in una rappresentazione protobuf standard.

## <a name="grpc-support-in-net"></a>supporto di gRPC in .NET

Il Framework di Microsoft .NET Core 3,0 include gli strumenti e il supporto nativo per gRPC. Nella figura 4-20 è illustrato il modello di Visual Studio 2019 che offre un'impalcatura di un progetto gRPC Skeleton per un servizio gRPC. Si noti che .NET Core supporta le piattaforme Windows, Linux e macOS.

![Supporto di gRPC in Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Figura 4-20**. supporto di gRPC in Visual Studio 2019

.NET Core 3,0 integra perfettamente gRPC nel Framework, inclusi il routing degli endpoint, il supporto predefinito di IoC e la registrazione. Il server Web gheppio open source supporta completamente le connessioni HTTP/2.

Nella figura 4-21 è illustrata la struttura di un servizio gRPC in Visual Studio 2019. Si noti come la struttura di cartelle includa le cartelle per i file proto e il codice del servizio.

![progetto gRPC in Visual Studio 2019](./media/grpc-project.png  )

**Figura 4-21**. progetto gRPC in Visual Studio 2019

## <a name="grpc-usage"></a>Utilizzo di gRPC

gRPC è particolarmente adatto per gli scenari seguenti:

- Comunicazione con bassa latenza e velocità effettiva elevata. gRPC è ideale per i microservizi leggeri in cui l'efficienza è fondamentale.
- Comunicazione in tempo reale da punto a punto. gRPC offre un supporto eccellente per lo streaming bidirezionale. i servizi gRPC possono eseguire il push dei messaggi in tempo reale senza polling.
- Ambienti poliglotti: gli strumenti gRPC supportano i linguaggi di sviluppo più diffusi, rendendola una scelta ottimale per gli ambienti multilingue.
- Ambienti vincolati alla rete: i messaggi gRPC vengono serializzati con protobuf, un formato di messaggio leggero. Un messaggio gRPC è sempre più piccolo di un messaggio JSON equivalente.

Al momento della stesura di questo libro, la maggior parte dei browser ha un supporto limitato per gRPC. gRPC USA in modo intensivo le funzionalità HTTP/2 e nessun browser fornisce il livello di controllo necessario per le richieste Web per supportare un client gRPC. gRPC viene in genere usato per la comunicazione tra microservizi interni e microservizi. La figura 4-22 illustra un modello di utilizzo semplice ma comune.

![Modelli di utilizzo di gRPC](./media/grpc-usage.png)

**Figura 4-22**. modelli di utilizzo di gRPC

Si noti che nella figura precedente viene richiamato il traffico front-end con HTTP mentre il microservizio back-end in microservizio USA gRPC.

In futuro, gRPC potrebbe svolgere un ruolo importante in detronizzare il dominamento di REST per i sistemi nativi del cloud. I vantaggi delle prestazioni e la facilità di sviluppo sono troppo efficaci per essere superati. Tuttavia, non creare alcun errore, REST rimarrà comunque da molto tempo. Si distingue ancora per le API esposte pubblicamente e per motivi di compatibilità con le versioni precedenti.

>[!div class="step-by-step"]
>[Precedente](service-to-service-communication.md)
>[Successivo](service-mesh-communication-infrastructure.md)
