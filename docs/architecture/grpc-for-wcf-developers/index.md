---
title: ASP.NET Core gRPC per sviluppatori WCF-gRPC per sviluppatori WCF
description: DA SCRIVERE
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 7d02d7914aed39613b4a41da55515df80abddfe8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184449"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="d904b-103">ASP.NET Core gRPC per sviluppatori WCF</span><span class="sxs-lookup"><span data-stu-id="d904b-103">ASP.NET Core gRPC for WCF Developers</span></span>

![Immagine di copertina](./media/cover.png)

<span data-ttu-id="d904b-105">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="d904b-105">PUBLISHED BY</span></span>

<span data-ttu-id="d904b-106">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d904b-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="d904b-107">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="d904b-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="d904b-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="d904b-108">One Microsoft Way</span></span>

<span data-ttu-id="d904b-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="d904b-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="d904b-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="d904b-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="d904b-111">Tutti i diritti sono riservati.</span><span class="sxs-lookup"><span data-stu-id="d904b-111">All rights reserved.</span></span> <span data-ttu-id="d904b-112">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="d904b-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="d904b-113">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="d904b-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="d904b-114">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="d904b-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="d904b-115">Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="d904b-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="d904b-116">Nessuna associazione o connessione reale è intenzionale o può essere presupposta.</span><span class="sxs-lookup"><span data-stu-id="d904b-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="d904b-117">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d904b-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="d904b-118">Il logo Docker con la balena è un marchio registrato di Docker, Inc. Usato su autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="d904b-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="d904b-119">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="d904b-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="d904b-120">Autore:</span><span class="sxs-lookup"><span data-stu-id="d904b-120">Author:</span></span>

> <span data-ttu-id="d904b-121">**Mark Rendle** -Chief Technical Officer- [Visual Recode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="d904b-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="d904b-122">**Miranda Steiner** -autore tecnico</span><span class="sxs-lookup"><span data-stu-id="d904b-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="d904b-123">Editor:</span><span class="sxs-lookup"><span data-stu-id="d904b-123">Editors:</span></span>

> <span data-ttu-id="d904b-124">**Maira Wenzel** -SR Content Developer-Microsoft</span><span class="sxs-lookup"><span data-stu-id="d904b-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="d904b-125">Introduzione</span><span class="sxs-lookup"><span data-stu-id="d904b-125">Introduction</span></span>

<span data-ttu-id="d904b-126">TODO</span><span class="sxs-lookup"><span data-stu-id="d904b-126">TODO</span></span>

## <a name="purpose"></a><span data-ttu-id="d904b-127">Scopo</span><span class="sxs-lookup"><span data-stu-id="d904b-127">Purpose</span></span>

<span data-ttu-id="d904b-128">TODO</span><span class="sxs-lookup"><span data-stu-id="d904b-128">TODO</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="d904b-129">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="d904b-129">Who should use this guide</span></span>

<span data-ttu-id="d904b-130">**AGGIORNA**</span><span class="sxs-lookup"><span data-stu-id="d904b-130">**UPDATE THIS**</span></span>

<span data-ttu-id="d904b-131">I destinatari di questa guida sono gli sviluppatori, i lead di sviluppo e gli architetti WCF interessati alla migrazione di soluzioni WCF in .NET 4 e versioni precedenti a ASP.NET Core 3,0 mediante i servizi gRPC.</span><span class="sxs-lookup"><span data-stu-id="d904b-131">The audience for this guide is WCF developers, development leads, and architects who are interested in migrating WCF solutions on .NET 4 and earlier to ASP.NET Core 3.0 using gRPC services.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="d904b-132">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="d904b-132">How you can use this guide</span></span>

<span data-ttu-id="d904b-133">**AGGIORNA**</span><span class="sxs-lookup"><span data-stu-id="d904b-133">**UPDATE THIS**</span></span>

<span data-ttu-id="d904b-134">Si tratta di una breve introduzione alla creazione di servizi gRPC in ASP.NET Core 3,0 con particolare riferimento a WCF come piattaforma analoga.</span><span class="sxs-lookup"><span data-stu-id="d904b-134">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="d904b-135">Vengono illustrati i principi di gRPC, con la correlazione di ogni concetto alle funzionalità equivalenti di WCF e vengono fornite indicazioni per la migrazione di un'applicazione WCF esistente a gRPC.</span><span class="sxs-lookup"><span data-stu-id="d904b-135">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="d904b-136">È utile anche per gli sviluppatori che hanno esperienza con WCF e vogliono apprendere gRPC per creare nuovi servizi.</span><span class="sxs-lookup"><span data-stu-id="d904b-136">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="d904b-137">L'applicazione di esempio può essere usata come modello o riferimento per i propri progetti e si è liberi di copiare e riutilizzare il codice dal libro o dai relativi esempi.</span><span class="sxs-lookup"><span data-stu-id="d904b-137">The sample application can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="d904b-138">È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità.</span><span class="sxs-lookup"><span data-stu-id="d904b-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="d904b-139">Facendo sì che tutti usino un insieme comune di termini e di principi sottostanti, si garantisce l'applicazione coerente di modelli e procedure architetturali.</span><span class="sxs-lookup"><span data-stu-id="d904b-139">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="d904b-140">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="d904b-140">References</span></span>

- <span data-ttu-id="d904b-141">**sito Web gRPC**</span><span class="sxs-lookup"><span data-stu-id="d904b-141">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="d904b-142">**Scelta di .NET Core o .NET Framework per le app server**</span><span class="sxs-lookup"><span data-stu-id="d904b-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="d904b-143">avanti</span><span class="sxs-lookup"><span data-stu-id="d904b-143">Next</span></span>](introduction.md)
