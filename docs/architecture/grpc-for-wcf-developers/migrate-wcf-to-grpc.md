---
title: Eseguire la migrazione di una soluzione WCF in gRPC-gRPC per sviluppatori WCF
description: Come eseguire la migrazione di tipi diversi di servizio WCF all'equivalente in gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 77bcb1412803b371778943763308c3010ed35aac
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72770108"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>Eseguire la migrazione di una soluzione WCF a gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In questo capitolo viene illustrato come utilizzare i progetti di ASP.NET Core 3,0 gRPC e viene illustrata la migrazione di diversi tipi di servizio WCF all'equivalente gRPC:

- Creare un progetto ASP.NET Core 3,0 gRPC.
- Semplici operazioni request/reply per gRPC la RPC unaria.
- Operazioni unidirezionali per la RPC in streaming client gRPC.
- Servizi duplex completi per gRPC RPC di streaming bidirezionale.

Viene inoltre utilizzato un confronto tra i servizi di streaming e i campi ripetuti per la restituzione di set di dati e l'utilizzo di librerie client alla fine del capitolo.

L'applicazione WCF di esempio è uno stub minimo di un set di servizi di trading azionario, usando la libreria di Contenitori IoC (Inversion of Control) Open Source denominata *Autofac* per l'inserimento delle dipendenze. Sono inclusi tre servizi, uno per ogni tipo di servizio WCF. I servizi verranno descritti più dettagliatamente nelle sezioni seguenti. Le soluzioni possono essere scaricate da [DotNet-Architecture/grpc-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) su GitHub. I servizi utilizzano dati fittizi per ridurre al minimo le dipendenze esterne.

Gli esempi includono le implementazioni WCF e gRPC di ogni servizio.

>[!div class="step-by-step"]
>[Precedente](ws-protocols.md)
>[Successivo](create-project.md)
