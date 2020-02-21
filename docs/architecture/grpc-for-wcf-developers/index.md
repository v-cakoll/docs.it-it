---
title: ASP.NET Core gRPC per sviluppatori WCF-gRPC per sviluppatori WCF
description: Introduzione alla compilazione di servizi gRPC in ASP.NET Core 3,0 per sviluppatori WCF
ms.date: 09/02/2019
ms.openlocfilehash: 40307124c521659a00339884bacf48881fa3e048
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543235"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="63867-103">ASP.NET Core gRPC per sviluppatori WCF</span><span class="sxs-lookup"><span data-stu-id="63867-103">ASP.NET Core gRPC for WCF Developers</span></span>

![Immagine di copertina](./media/cover.png)

<span data-ttu-id="63867-105">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="63867-105">PUBLISHED BY</span></span>

<span data-ttu-id="63867-106">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63867-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="63867-107">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="63867-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="63867-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="63867-108">One Microsoft Way</span></span>

<span data-ttu-id="63867-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="63867-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="63867-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="63867-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="63867-111">Tutti i diritti riservati.</span><span class="sxs-lookup"><span data-stu-id="63867-111">All rights reserved.</span></span> <span data-ttu-id="63867-112">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="63867-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="63867-113">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="63867-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="63867-114">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="63867-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="63867-115">Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="63867-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="63867-116">Nessuna associazione o connessione reale è intenzionale o può essere presupposta.</span><span class="sxs-lookup"><span data-stu-id="63867-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="63867-117">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="63867-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="63867-118">Il logo Docker Whale è un marchio registrato di Docker, Inc. usato dall'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="63867-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="63867-119">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="63867-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="63867-120">Autori:</span><span class="sxs-lookup"><span data-stu-id="63867-120">Authors:</span></span>

> <span data-ttu-id="63867-121">**Mark Rendle** -Chief Technical Officer- [Visual Recode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="63867-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="63867-122">**Miranda Steiner** -autore tecnico</span><span class="sxs-lookup"><span data-stu-id="63867-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="63867-123">Editore:</span><span class="sxs-lookup"><span data-stu-id="63867-123">Editor:</span></span>

> <span data-ttu-id="63867-124">**Maira Wenzel** -SR. Content Developer-Microsoft</span><span class="sxs-lookup"><span data-stu-id="63867-124">**Maira Wenzel** - Sr. Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="63867-125">Introduzione</span><span class="sxs-lookup"><span data-stu-id="63867-125">Introduction</span></span>

<span data-ttu-id="63867-126">gRPC è un Framework moderno per la creazione di servizi di rete e applicazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="63867-126">gRPC is a modern framework for building networked services and distributed applications.</span></span> <span data-ttu-id="63867-127">Immaginate le prestazioni delle associazioni Windows Communication Foundation (WCF) NetTCP, combinate con l'interoperabilità multipiattaforma di SOAP.</span><span class="sxs-lookup"><span data-stu-id="63867-127">Imagine the performance of Windows Communication Foundation (WCF) NetTCP bindings, combined with the cross-platform interoperability of SOAP.</span></span> <span data-ttu-id="63867-128">gRPC si basa su HTTP/2 e sul protocollo di codifica dei messaggi protobuf per offrire una comunicazione a larghezza di banda ridotta e prestazioni elevate tra le applicazioni e i servizi.</span><span class="sxs-lookup"><span data-stu-id="63867-128">gRPC builds on HTTP/2 and the Protobuf message-encoding protocol to provide high performance, low-bandwidth communication between applications and services.</span></span> <span data-ttu-id="63867-129">Supporta la generazione di codice server e client tra le piattaforme e i linguaggi di programmazione più diffusi, tra cui .NET, Java, Python, node. C++js, go e.</span><span class="sxs-lookup"><span data-stu-id="63867-129">It supports server and client code generation across most popular programming languages and platforms, including .NET, Java, Python, Node.js, Go, and C++.</span></span> <span data-ttu-id="63867-130">Con il supporto di prima classe per gRPC in ASP.NET Core 3,0, insieme agli strumenti e alle librerie gRPC esistenti per .NET 4. x, è un'ottima alternativa a WCF per i team di sviluppo che vogliono adottare .NET Core nelle proprie organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="63867-130">With the first-class support for gRPC in ASP.NET Core 3.0, alongside the existing gRPC tools and libraries for .NET 4.x, it's an excellent alternative to WCF for development teams looking to adopt .NET Core in their organizations.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="63867-131">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="63867-131">Who should use this guide</span></span>

<span data-ttu-id="63867-132">Questa guida è stata scritta per gli sviluppatori che lavorano in .NET Framework o .NET Core che hanno usato in precedenza WCF e che stanno tentando di eseguire la migrazione delle applicazioni a un ambiente RPC moderno per .NET Core 3,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="63867-132">This guide was written for developers working in .NET Framework or .NET Core who have previously used WCF, and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="63867-133">Più in generale, se si esegue l'aggiornamento o si sta valutando l'aggiornamento a .NET Core 3,0 e si vuole usare gli strumenti gRPC predefiniti, questa guida è anche utile.</span><span class="sxs-lookup"><span data-stu-id="63867-133">More generally, if you are upgrading, or considering upgrading, to .NET Core 3.0, and you want to use the built-in gRPC tools, this guide is also useful.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="63867-134">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="63867-134">How you can use this guide</span></span>

<span data-ttu-id="63867-135">Si tratta di una breve introduzione alla creazione di servizi gRPC in ASP.NET Core 3,0, con particolare riferimento a WCF come piattaforma analoga.</span><span class="sxs-lookup"><span data-stu-id="63867-135">This is a short introduction to building gRPC Services in ASP.NET Core 3.0, with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="63867-136">Vengono illustrati i principi di gRPC, con la correlazione di ogni concetto alle funzionalità equivalenti di WCF e vengono fornite indicazioni per la migrazione di un'applicazione WCF esistente a gRPC.</span><span class="sxs-lookup"><span data-stu-id="63867-136">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="63867-137">Questa funzionalità è utile anche per gli sviluppatori che hanno esperienza con WCF e vogliono imparare a usare gRPC per creare nuovi servizi.</span><span class="sxs-lookup"><span data-stu-id="63867-137">It's also useful for developers who have experience with WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="63867-138">È possibile utilizzare le applicazioni di esempio come modello o riferimento per i propri progetti e si è liberi di copiare e riutilizzare il codice dal libro o dai relativi esempi.</span><span class="sxs-lookup"><span data-stu-id="63867-138">You can use the sample applications as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="63867-139">È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità.</span><span class="sxs-lookup"><span data-stu-id="63867-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="63867-140">L'uso di un set comune di termini e di principi sottostanti contribuisce a garantire un'applicazione coerente di modelli e procedure di architettura.</span><span class="sxs-lookup"><span data-stu-id="63867-140">Having everybody working from a common set of terms and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="63867-141">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="63867-141">References</span></span>

- <span data-ttu-id="63867-142">**sito Web di gRPC**
  <https://grpc.io></span><span class="sxs-lookup"><span data-stu-id="63867-142">**gRPC website**
<https://grpc.io></span></span>
- <span data-ttu-id="63867-143">**Scelta tra .NET Core e .NET Framework per le app server**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="63867-143">**Choosing between .NET Core and .NET Framework for server apps**
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="63867-144">avanti</span><span class="sxs-lookup"><span data-stu-id="63867-144">Next</span></span>](introduction.md)
