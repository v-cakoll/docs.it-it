---
title: Eseguire la migrazione di una soluzione WCF in gRPC-gRPC per sviluppatori WCF
description: Come eseguire la migrazione di tipi diversi di servizi WCF all'equivalente in gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 12e724ab46a33547d352da7a604a5a994e617bc2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628514"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a>Eseguire la migrazione di una soluzione WCF a gRPC

In questo capitolo viene descritto come utilizzare ASP.NET Core 3,0 progetti gRPC e viene illustrata la migrazione di diversi tipi di servizi di Windows Communication Foundation (WCF) all'equivalente gRPC:

- Creare un progetto ASP.NET Core 3,0 gRPC.
- Semplici operazioni request/reply per gRPC la RPC unaria.
- Operazioni unidirezionali per la RPC in streaming client gRPC.
- Servizi full-duplex per gRPC RPC di streaming bidirezionale.

È inoltre disponibile un confronto tra l'utilizzo di servizi di streaming e i campi ripetuti per la restituzione di set di impostazioni ed è disponibile una discussione sull'utilizzo delle librerie client alla fine del capitolo.

L'applicazione WCF di esempio è uno stub minimo di un set di servizi di trading azionario. Usa la libreria di Contenitori IoC (Inversion of Control) Open Source denominata Autofac per l'inserimento delle dipendenze. Sono inclusi tre servizi, uno per ogni tipo di servizio WCF. I servizi verranno descritti più dettagliatamente nelle sezioni seguenti. È possibile scaricare le soluzioni da [DotNet-Architecture/grpc-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) su GitHub. I servizi utilizzano dati fittizi per ridurre al minimo le dipendenze esterne.

Gli esempi includono le implementazioni WCF e gRPC di ogni servizio.

>[!div class="step-by-step"]
>[Precedente](ws-protocols.md)
>[Successivo](create-project.md)
