---
title: Panoramica di gRPC-gRPC per sviluppatori WCF
description: Informazioni sul set di principi che guidano lo sviluppo di gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 489b91f6aa279d9c457e2e8fccd4438885076779
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72770456"
---
# <a name="grpc-overview"></a><span data-ttu-id="e1228-103">Panoramica di gRPC</span><span class="sxs-lookup"><span data-stu-id="e1228-103">gRPC overview</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e1228-104">Dopo aver esaminato la genesi di WCF e gRPC nell'ultimo capitolo, in questo capitolo verranno prese in considerazione alcune delle funzionalità principali di gRPC e il modo in cui vengono confrontate con WCF.</span><span class="sxs-lookup"><span data-stu-id="e1228-104">After looking at the genesis of both WCF and gRPC in the last chapter, this chapter will consider some of the key features of gRPC and how they compare to WCF.</span></span>

<span data-ttu-id="e1228-105">ASP.NET Core 3,0 è la prima versione di ASP.NET che supporta in modo nativo gRPC come un cittadino di prima classe, con i team Microsoft che contribuiscono all'implementazione di .NET ufficiale di gRPC.</span><span class="sxs-lookup"><span data-stu-id="e1228-105">ASP.NET Core 3.0 is the first release of ASP.NET that natively supports gRPC as a first-class citizen, with Microsoft teams contributing to the official .NET implementation of gRPC.</span></span> <span data-ttu-id="e1228-106">Si tratta di un approccio consigliato per la creazione di applicazioni distribuite con .NET in grado di interagire con tutti gli altri linguaggi e Framework di programmazione principali.</span><span class="sxs-lookup"><span data-stu-id="e1228-106">It's recommended as the best approach for building distributed applications with .NET that can interoperate with all other major programming languages and frameworks.</span></span>

## <a name="key-principles"></a><span data-ttu-id="e1228-107">Principi chiave</span><span class="sxs-lookup"><span data-stu-id="e1228-107">Key principles</span></span>

<span data-ttu-id="e1228-108">Come illustrato nel capitolo 1, Google ha voluto usare l'introduzione di HTTP/2 per sostituire Stubby, l'infrastruttura RPC per utilizzo generico interna.</span><span class="sxs-lookup"><span data-stu-id="e1228-108">As discussed in chapter 1, Google wanted to use the introduction of HTTP/2 to replace Stubby, its internal, general purpose RPC infrastructure.</span></span> <span data-ttu-id="e1228-109">gRPC, basato su Stubby, ora può sfruttare i vantaggi della standardizzazione ed estendere la relativa applicabilità al mobile computing, al cloud e al Internet delle cose.</span><span class="sxs-lookup"><span data-stu-id="e1228-109">gRPC, based on Stubby, now could take advantage of standardization and would extend its applicability to mobile computing, the cloud, and the Internet of Things.</span></span>

<span data-ttu-id="e1228-110">A tale scopo, il [cloud native Computing Foundation (CNCF)](https://www.cncf.io/) ha stabilito un set di principi che governano gRPC.</span><span class="sxs-lookup"><span data-stu-id="e1228-110">To achieve this, the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) established a set of principles that would govern gRPC.</span></span> <span data-ttu-id="e1228-111">Nell'elenco seguente sono illustrati i più rilevanti, che riguardano principalmente la massimizzazione dell'accessibilità e dell'usabilità:</span><span class="sxs-lookup"><span data-stu-id="e1228-111">The following list shows the most relevant ones, which are mainly concerned with maximizing accessibility and usability:</span></span>

- <span data-ttu-id="e1228-112">**Gratuito e aperto** : tutti gli elementi devono essere open source con licenze che non vincolano gli sviluppatori all'adozione di gRPC.</span><span class="sxs-lookup"><span data-stu-id="e1228-112">**Free and open** – all artifacts should be open source with licensing that doesn't constrain developers from adopting gRPC.</span></span>
- <span data-ttu-id="e1228-113">**Code coverage e semplicità** : gRPC dovrebbe essere disponibile in tutte le piattaforme più diffuse e abbastanza semplice da creare su qualsiasi piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e1228-113">**Coverage and simplicity** – gRPC should be available across every popular platform and simple enough to build on any platform.</span></span>
- <span data-ttu-id="e1228-114">**Interoperabilità e REACH** : dovrebbe essere possibile usare gRPC in qualsiasi rete, indipendentemente dalla larghezza di banda o dalla latenza, usando gli standard di rete ampiamente disponibili.</span><span class="sxs-lookup"><span data-stu-id="e1228-114">**Interoperability and reach** – it should be possible to use gRPC on any network, regardless of bandwidth or latency, using widely available network standards.</span></span>
- <span data-ttu-id="e1228-115">Utilizzo **generico ed efficiente** : il Framework deve essere utilizzabile in un'ampia gamma di casi d'uso possibili senza compromettere le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e1228-115">**General purpose and performant** – the framework should be usable by as broad a range of use-cases as possible without compromising performance.</span></span>
- <span data-ttu-id="e1228-116">**Streaming** : il protocollo deve fornire la semantica di flusso per set di dati di grandi dimensioni o messaggistica asincrona.</span><span class="sxs-lookup"><span data-stu-id="e1228-116">**Streaming** – the protocol should provide streaming semantics for large data-sets or asynchronous messaging.</span></span>
- <span data-ttu-id="e1228-117">**Scambio di metadati** : il protocollo consente ai dati non aziendali, ad esempio i token di autenticazione, di essere gestiti separatamente dai dati aziendali effettivi.</span><span class="sxs-lookup"><span data-stu-id="e1228-117">**Metadata exchange** – the protocol allow non-business data, such as authentication tokens, to be handled separately from actual business data.</span></span>
- <span data-ttu-id="e1228-118">**Codici di stato standardizzati** : la variabilità dei codici di errore deve essere ridotta per semplificare le decisioni di gestione degli errori e, in cui è necessaria una gestione degli errori più completa, è necessario fornire un meccanismo per gestirlo nello scambio di metadati.</span><span class="sxs-lookup"><span data-stu-id="e1228-118">**Standardized status codes** – the variability of error codes should be reduced to make error handling decisions clearer and, where additional richer error handling is required, a mechanism should be provided for managing this within the metadata exchange.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e1228-119">[Precedente](introduction.md)
>[Successivo](approach.md)</span><span class="sxs-lookup"><span data-stu-id="e1228-119">[Previous](introduction.md)
[Next](approach.md)</span></span>
