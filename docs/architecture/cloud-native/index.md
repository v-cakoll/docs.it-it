---
title: Architettura di applicazioni .NET cloud native per Azure
description: Guida per la creazione di applicazioni native del cloud che sfruttano contenitori, microservizi e funzionalità senza server di Azure.
author: ardalis
ms.date: 05/13/2020
ms.openlocfilehash: 172097b4915deb2d6f0b06441d7c4ca389bbca25
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051506"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="519d8-103">Architettura di applicazioni .NET cloud native per Azure</span><span class="sxs-lookup"><span data-stu-id="519d8-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![Immagine di copertina](./media/cover.png)

<span data-ttu-id="519d8-105">**EDIZIONE v. 1.0**</span><span class="sxs-lookup"><span data-stu-id="519d8-105">**EDITION v.1.0**</span></span>

<span data-ttu-id="519d8-106">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="519d8-106">PUBLISHED BY</span></span>

<span data-ttu-id="519d8-107">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="519d8-107">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="519d8-108">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="519d8-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="519d8-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="519d8-109">One Microsoft Way</span></span>

<span data-ttu-id="519d8-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="519d8-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="519d8-111">Copyright &copy; 2020 di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="519d8-111">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="519d8-112">Tutti i diritti sono riservati.</span><span class="sxs-lookup"><span data-stu-id="519d8-112">All rights reserved.</span></span> <span data-ttu-id="519d8-113">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="519d8-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="519d8-114">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="519d8-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="519d8-115">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="519d8-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="519d8-116"> Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="519d8-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="519d8-117">Nessuna associazione reale o connessione è intenzionale o può essere desunta.</span><span class="sxs-lookup"><span data-stu-id="519d8-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="519d8-118">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="519d8-118">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="519d8-119">Mac e macOS sono marchi registrati di Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="519d8-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="519d8-120">Il logo Docker Whale è un marchio registrato di Docker, Inc. usato dall'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="519d8-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="519d8-121">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="519d8-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="519d8-122">Autori:</span><span class="sxs-lookup"><span data-stu-id="519d8-122">Authors:</span></span>

> <span data-ttu-id="519d8-123">**Rob Vettor**, Principal Cloud System Architect/IP architect- [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span><span class="sxs-lookup"><span data-stu-id="519d8-123">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="519d8-124">**Steve "ardalis" Smith**, Software Architect e Trainer- [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="519d8-124">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="519d8-125">Partecipanti e revisori:</span><span class="sxs-lookup"><span data-stu-id="519d8-125">Participants and Reviewers:</span></span>

> <span data-ttu-id="519d8-126">**Cesar de la Torre**, responsabile del programma principale, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="519d8-126">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="519d8-127">**Nitura Anil**, Senior Program Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="519d8-127">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="519d8-128">**Jeremy Likness**, Senior Program Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="519d8-128">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="519d8-129">**Cecil Phillip**, senior cloud Advocate, Microsoft</span><span class="sxs-lookup"><span data-stu-id="519d8-129">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="519d8-130">Editor:</span><span class="sxs-lookup"><span data-stu-id="519d8-130">Editors:</span></span>

> <span data-ttu-id="519d8-131">**Maira Wenzel**, Program Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="519d8-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="519d8-132">Versione</span><span class="sxs-lookup"><span data-stu-id="519d8-132">Version</span></span>

<span data-ttu-id="519d8-133">Questa guida è stata scritta per coprire la versione di **.net core 3,1** insieme a molti aggiornamenti aggiuntivi relativi alla stessa "Wave" delle tecnologie (ovvero, Azure e altre tecnologie di terze parti) in concomitanza con la versione di .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="519d8-133">This guide has been written to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="519d8-134">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="519d8-134">Who should use this guide</span></span>

<span data-ttu-id="519d8-135">I destinatari di questa guida sono principalmente sviluppatori, lead di sviluppo e architetti che sono interessati ad apprendere come creare applicazioni progettate per il cloud.</span><span class="sxs-lookup"><span data-stu-id="519d8-135">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="519d8-136">Un pubblico secondario è costituito da Decision Maker tecnici che pianificano di scegliere se compilare le proprie applicazioni usando un approccio nativo per il cloud.</span><span class="sxs-lookup"><span data-stu-id="519d8-136">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="519d8-137">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="519d8-137">How you can use this guide</span></span>

<span data-ttu-id="519d8-138">Questa guida inizia definendo cloud native e introducendo un'applicazione di riferimento compilata usando principi e tecnologie native del cloud.</span><span class="sxs-lookup"><span data-stu-id="519d8-138">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="519d8-139">Oltre a questi primi due capitoli, il resto del libro è suddiviso in capitoli specifici che riguardano argomenti comuni alla maggior parte delle applicazioni native del cloud.</span><span class="sxs-lookup"><span data-stu-id="519d8-139">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="519d8-140">È possibile passare a uno di questi capitoli per ottenere informazioni sugli approcci nativi del cloud per:</span><span class="sxs-lookup"><span data-stu-id="519d8-140">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="519d8-141">Accesso ai dati e ai dati</span><span class="sxs-lookup"><span data-stu-id="519d8-141">Data and data access</span></span>
- <span data-ttu-id="519d8-142">Modelli di comunicazione</span><span class="sxs-lookup"><span data-stu-id="519d8-142">Communication patterns</span></span>
- <span data-ttu-id="519d8-143">Scalabilità e scalabilità</span><span class="sxs-lookup"><span data-stu-id="519d8-143">Scaling and scalability</span></span>
- <span data-ttu-id="519d8-144">Resilienza delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="519d8-144">Application resiliency</span></span>
- <span data-ttu-id="519d8-145">Monitoraggio e integrità</span><span class="sxs-lookup"><span data-stu-id="519d8-145">Monitoring and health</span></span>
- <span data-ttu-id="519d8-146">Identità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="519d8-146">Identity and security</span></span>
- <span data-ttu-id="519d8-147">DevOps</span><span class="sxs-lookup"><span data-stu-id="519d8-147">DevOps</span></span>

<span data-ttu-id="519d8-148">Questa guida è disponibile sia in formato [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) che in linea.</span><span class="sxs-lookup"><span data-stu-id="519d8-148">This guide is available both in [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) form and online.</span></span> <span data-ttu-id="519d8-149">È possibile inviare questo documento o collegamenti alla relativa versione online al team per garantire una conoscenza comune di questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="519d8-149">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="519d8-150">La maggior parte di questi argomenti trae vantaggio da una comprensione coerente dei principi e dei modelli sottostanti, nonché dei compromessi che interessano le decisioni correlate a questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="519d8-150">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="519d8-151">Il nostro obiettivo di questo documento è quello di dotare i team e i loro leader con le informazioni necessarie per prendere decisioni ben informate per l'architettura, lo sviluppo e l'hosting delle proprie applicazioni.</span><span class="sxs-lookup"><span data-stu-id="519d8-151">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="519d8-152">Invia commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="519d8-152">Send your feedback</span></span>

<span data-ttu-id="519d8-153">Questo libro ed esempi correlati sono in continua evoluzione, quindi il feedback è stato accolto.</span><span class="sxs-lookup"><span data-stu-id="519d8-153">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="519d8-154">Per Commenti su come migliorare questo libro, usare la sezione feedback nella parte inferiore di qualsiasi pagina basata su [problemi di GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="519d8-154">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="519d8-155">Avanti</span><span class="sxs-lookup"><span data-stu-id="519d8-155">Next</span></span>](introduction.md)
