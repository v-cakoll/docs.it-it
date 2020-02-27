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
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="9b197-103">Eseguire la migrazione di una soluzione WCF a gRPC</span><span class="sxs-lookup"><span data-stu-id="9b197-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="9b197-104">In questo capitolo viene descritto come utilizzare ASP.NET Core 3,0 progetti gRPC e viene illustrata la migrazione di diversi tipi di servizi di Windows Communication Foundation (WCF) all'equivalente gRPC:</span><span class="sxs-lookup"><span data-stu-id="9b197-104">This chapter will describe how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of Windows Communication Foundation (WCF) services to the gRPC equivalent:</span></span>

- <span data-ttu-id="9b197-105">Creare un progetto ASP.NET Core 3,0 gRPC.</span><span class="sxs-lookup"><span data-stu-id="9b197-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="9b197-106">Semplici operazioni request/reply per gRPC la RPC unaria.</span><span class="sxs-lookup"><span data-stu-id="9b197-106">Simple request-reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="9b197-107">Operazioni unidirezionali per la RPC in streaming client gRPC.</span><span class="sxs-lookup"><span data-stu-id="9b197-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="9b197-108">Servizi full-duplex per gRPC RPC di streaming bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9b197-108">Full-duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="9b197-109">È inoltre disponibile un confronto tra l'utilizzo di servizi di streaming e i campi ripetuti per la restituzione di set di impostazioni ed è disponibile una discussione sull'utilizzo delle librerie client alla fine del capitolo.</span><span class="sxs-lookup"><span data-stu-id="9b197-109">There's also a comparison of using streaming services versus repeated fields for returning datasets, and there's a discussion of the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="9b197-110">L'applicazione WCF di esempio è uno stub minimo di un set di servizi di trading azionario.</span><span class="sxs-lookup"><span data-stu-id="9b197-110">The sample WCF application is a minimal stub of a set of stock trading services.</span></span> <span data-ttu-id="9b197-111">Usa la libreria di Contenitori IoC (Inversion of Control) Open Source denominata Autofac per l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="9b197-111">It uses the open-source Inversion of Control (IoC) container library called Autofac for dependency injection.</span></span> <span data-ttu-id="9b197-112">Sono inclusi tre servizi, uno per ogni tipo di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="9b197-112">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="9b197-113">I servizi verranno descritti più dettagliatamente nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9b197-113">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="9b197-114">È possibile scaricare le soluzioni da [DotNet-Architecture/grpc-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="9b197-114">You can download the solutions from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="9b197-115">I servizi utilizzano dati fittizi per ridurre al minimo le dipendenze esterne.</span><span class="sxs-lookup"><span data-stu-id="9b197-115">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="9b197-116">Gli esempi includono le implementazioni WCF e gRPC di ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="9b197-116">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9b197-117">[Precedente](ws-protocols.md)
>[Successivo](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="9b197-117">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
