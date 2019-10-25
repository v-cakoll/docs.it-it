---
title: Eseguire la migrazione di una soluzione WCF in gRPC-gRPC per sviluppatori WCF
description: Come eseguire la migrazione di tipi diversi di servizio WCF all'equivalente in gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 65c30b777d9981cb3291b846f698f2a69b4498fc
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846596"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="5cf7c-103">Eseguire la migrazione di una soluzione WCF a gRPC</span><span class="sxs-lookup"><span data-stu-id="5cf7c-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="5cf7c-104">In questo capitolo viene illustrato come utilizzare i progetti di ASP.NET Core 3,0 gRPC e viene illustrata la migrazione di diversi tipi di servizio WCF all'equivalente gRPC:</span><span class="sxs-lookup"><span data-stu-id="5cf7c-104">This chapter will look at how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of WCF service to the gRPC equivalent:</span></span>

- <span data-ttu-id="5cf7c-105">Creare un progetto ASP.NET Core 3,0 gRPC.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="5cf7c-106">Semplici operazioni request/reply per gRPC la RPC unaria.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-106">Simple Request-Reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="5cf7c-107">Operazioni unidirezionali per la RPC in streaming client gRPC.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="5cf7c-108">Servizi duplex completi per gRPC RPC di streaming bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-108">Full Duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="5cf7c-109">Viene inoltre utilizzato un confronto tra i servizi di streaming e i campi ripetuti per la restituzione di set di dati e l'utilizzo di librerie client alla fine del capitolo.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-109">There's also a comparison of using streaming services versus repeated fields for returning data sets, and the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="5cf7c-110">L'applicazione WCF di esempio è uno stub minimo di un set di servizi di trading azionario, usando la libreria di Contenitori IoC (Inversion of Control) Open Source denominata *Autofac* per l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-110">The sample WCF application is a minimal stub of a set of stock trading services, using the open-source Inversion of Control (IoC) container library called *Autofac* for dependency injection.</span></span> <span data-ttu-id="5cf7c-111">Sono inclusi tre servizi, uno per ogni tipo di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-111">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="5cf7c-112">I servizi verranno descritti più dettagliatamente nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-112">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="5cf7c-113">Le soluzioni possono essere scaricate da [DotNet-Architecture/grpc-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-113">The solutions can be downloaded from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="5cf7c-114">I servizi utilizzano dati fittizi per ridurre al minimo le dipendenze esterne.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-114">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="5cf7c-115">Gli esempi includono le implementazioni WCF e gRPC di ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="5cf7c-115">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5cf7c-116">[Precedente](ws-protocols.md)
>[Successivo](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="5cf7c-116">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
