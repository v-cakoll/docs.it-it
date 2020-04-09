---
title: ASP.NET Core gRPC per gli sviluppatori WCF - gRPC per gli sviluppatori WCF
description: Introduzione alla creazione di servizi gRPC in ASP.NET Core 3.0 per gli sviluppatori WCFIntroduction to building gRPC services in ASP.NET Core 3.0 for WCF developers
ms.date: 09/02/2019
ms.openlocfilehash: 175dfbf1880a0937615543c248fba3bed0e25c23
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988960"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="20363-103">ASP.NET Core gRPC per sviluppatori WCF</span><span class="sxs-lookup"><span data-stu-id="20363-103">ASP.NET Core gRPC for WCF Developers</span></span>

![Immagine di copertina](./media/cover.png)

<span data-ttu-id="20363-105">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="20363-105">PUBLISHED BY</span></span>

<span data-ttu-id="20363-106">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20363-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="20363-107">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="20363-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="20363-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="20363-108">One Microsoft Way</span></span>

<span data-ttu-id="20363-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="20363-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="20363-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="20363-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="20363-111">Tutti i diritti sono riservati.</span><span class="sxs-lookup"><span data-stu-id="20363-111">All rights reserved.</span></span> <span data-ttu-id="20363-112">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="20363-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="20363-113">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="20363-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="20363-114">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="20363-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="20363-115"> Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="20363-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="20363-116">Nessuna associazione reale o connessione è intenzionale o può essere desunta.</span><span class="sxs-lookup"><span data-stu-id="20363-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="20363-117">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20363-117">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="20363-118">Il logo Docker whale è un marchio registrato di Docker, Inc.</span><span class="sxs-lookup"><span data-stu-id="20363-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="20363-119">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="20363-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="20363-120">Autori:</span><span class="sxs-lookup"><span data-stu-id="20363-120">Authors:</span></span>

> <span data-ttu-id="20363-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="20363-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="20363-122">**Miranda Steiner** - Autore Tecnico</span><span class="sxs-lookup"><span data-stu-id="20363-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="20363-123">Editor:</span><span class="sxs-lookup"><span data-stu-id="20363-123">Editor:</span></span>

> <span data-ttu-id="20363-124">**Maira Wenzel** - Sr. Content Developer - Microsoft</span><span class="sxs-lookup"><span data-stu-id="20363-124">**Maira Wenzel** - Sr. Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="20363-125">Introduzione</span><span class="sxs-lookup"><span data-stu-id="20363-125">Introduction</span></span>

<span data-ttu-id="20363-126">gRPC è un framework moderno per la creazione di servizi in rete e applicazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="20363-126">gRPC is a modern framework for building networked services and distributed applications.</span></span> <span data-ttu-id="20363-127">Si immaginino le prestazioni delle associazioni NetTCP di Windows Communication Foundation (WCF), combinate con l'interoperabilità multipiattaforma di SOAP.</span><span class="sxs-lookup"><span data-stu-id="20363-127">Imagine the performance of Windows Communication Foundation (WCF) NetTCP bindings, combined with the cross-platform interoperability of SOAP.</span></span> <span data-ttu-id="20363-128">gRPC si basa su HTTP/2 e sul protocollo di codifica dei messaggi Protobuf per fornire comunicazioni ad alte prestazioni e a larghezza di banda ridotta tra applicazioni e servizi.</span><span class="sxs-lookup"><span data-stu-id="20363-128">gRPC builds on HTTP/2 and the Protobuf message-encoding protocol to provide high performance, low-bandwidth communication between applications and services.</span></span> <span data-ttu-id="20363-129">Supporta la generazione di codice server e client tra i linguaggi di programmazione più diffusi e le piattaforme, tra cui .NET, Java, Python, Node.js, Go e C .</span><span class="sxs-lookup"><span data-stu-id="20363-129">It supports server and client code generation across most popular programming languages and platforms, including .NET, Java, Python, Node.js, Go, and C++.</span></span> <span data-ttu-id="20363-130">Con il supporto di prima classe per gRPC in ASP.NET Core 3.0, insieme agli strumenti e alle librerie gRPC esistenti per .NET 4.x, è un'ottima alternativa a WCF per i team di sviluppo che desiderano adottare .NET Core nelle proprie organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="20363-130">With the first-class support for gRPC in ASP.NET Core 3.0, alongside the existing gRPC tools and libraries for .NET 4.x, it's an excellent alternative to WCF for development teams looking to adopt .NET Core in their organizations.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="20363-131">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="20363-131">Who should use this guide</span></span>

<span data-ttu-id="20363-132">Questa guida è stata scritta per gli sviluppatori che lavorano in .NET Framework o .NET Core che hanno utilizzato in precedenza WCF e che stanno cercando di eseguire la migrazione delle applicazioni in un ambiente RPC moderno per .NET Core 3.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="20363-132">This guide was written for developers working in .NET Framework or .NET Core who have previously used WCF, and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="20363-133">Più in generale, se si esegue l'aggiornamento o si sta valutando l'aggiornamento a .NET Core 3.0 e si desidera utilizzare gli strumenti gRPC incorporati, questa guida è utile.</span><span class="sxs-lookup"><span data-stu-id="20363-133">More generally, if you are upgrading, or considering upgrading, to .NET Core 3.0, and you want to use the built-in gRPC tools, this guide is also useful.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="20363-134">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="20363-134">How you can use this guide</span></span>

<span data-ttu-id="20363-135">Si tratta di una breve introduzione alla creazione di servizi gRPC in ASP.NET Core 3.0, con particolare riferimento a WCF come piattaforma analoga.</span><span class="sxs-lookup"><span data-stu-id="20363-135">This is a short introduction to building gRPC Services in ASP.NET Core 3.0, with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="20363-136">Vengono illustrati i principi di gRPC, si correlano ogni concetto alle funzionalità equivalenti di WCF e vengono fornite indicazioni per la migrazione di un'applicazione WCF esistente a gRPC.</span><span class="sxs-lookup"><span data-stu-id="20363-136">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="20363-137">È utile anche per gli sviluppatori che hanno esperienza con WCF e stanno cercando di imparare gRPC per creare nuovi servizi.</span><span class="sxs-lookup"><span data-stu-id="20363-137">It's also useful for developers who have experience with WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="20363-138">È possibile utilizzare le applicazioni di esempio come modello o riferimento per i propri progetti e si è liberi di copiare e riutilizzare il codice dal libro o dai relativi esempi.</span><span class="sxs-lookup"><span data-stu-id="20363-138">You can use the sample applications as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="20363-139">È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità.</span><span class="sxs-lookup"><span data-stu-id="20363-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="20363-140">Avere tutti coloro che lavorano da un insieme comune di termini e principi sottostanti aiuta a garantire un'applicazione coerente dei modelli e delle pratiche architettoniche.</span><span class="sxs-lookup"><span data-stu-id="20363-140">Having everybody working from a common set of terms and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="20363-141">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="20363-141">References</span></span>

- <span data-ttu-id="20363-142">**Sito Web gRPC**
  <https://grpc.io></span><span class="sxs-lookup"><span data-stu-id="20363-142">**gRPC website**
<https://grpc.io></span></span>
- <span data-ttu-id="20363-143">**Scelta tra .NET Core e .NET Framework per le app server**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="20363-143">**Choosing between .NET Core and .NET Framework for server apps**
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="20363-144">Avanti</span><span class="sxs-lookup"><span data-stu-id="20363-144">Next</span></span>](introduction.md)
