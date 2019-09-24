---
title: Architettura di applicazioni .NET cloud native per Azure
description: Guida per la creazione di applicazioni native del cloud che sfruttano contenitori, microservizi e funzionalità senza server di Azure.
author: ardalis
ms.date: 03/07/2019
ms.openlocfilehash: 67e235b051702308d2455b2501bfb59a4317635b
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214160"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="7f2a8-103">Architettura di applicazioni .NET cloud native per Azure</span><span class="sxs-lookup"><span data-stu-id="7f2a8-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![Immagine di copertina](./media/cover.png)

<span data-ttu-id="7f2a8-105">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="7f2a8-105">PUBLISHED BY</span></span>

<span data-ttu-id="7f2a8-106">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7f2a8-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="7f2a8-107">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="7f2a8-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="7f2a8-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="7f2a8-108">One Microsoft Way</span></span>

<span data-ttu-id="7f2a8-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="7f2a8-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="7f2a8-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="7f2a8-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="7f2a8-111">Tutti i diritti sono riservati.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-111">All rights reserved.</span></span> <span data-ttu-id="7f2a8-112">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="7f2a8-113">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="7f2a8-114">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="7f2a8-115">Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="7f2a8-116">Nessuna associazione o connessione reale è intenzionale o può essere presupposta.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="7f2a8-117">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="7f2a8-118">Mac e macOS sono marchi registrati di Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="7f2a8-119">Il logo Docker con la balena è un marchio registrato di Docker, Inc. Usato su autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="7f2a8-120">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="7f2a8-121">Autori</span><span class="sxs-lookup"><span data-stu-id="7f2a8-121">Authors:</span></span>

> <span data-ttu-id="7f2a8-122">**Steve "ardalis" Smith** - Software Architect e Trainer - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="7f2a8-122">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="7f2a8-123">**Rob Vettor** -Microsoft-Principal Cloud System Architect/IP architect- [RobVettor.com](https://robvettor.com)</span><span class="sxs-lookup"><span data-stu-id="7f2a8-123">**Rob Vettor** - Microsoft - Principal Cloud System Architect/IP Architect - [RobVettor.com](https://robvettor.com)</span></span>

<span data-ttu-id="7f2a8-124">Partecipanti e revisori:</span><span class="sxs-lookup"><span data-stu-id="7f2a8-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="7f2a8-125">**Cesar de la Torre**, responsabile del programma principale, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f2a8-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="7f2a8-126">**Nish Anil**, Senior Program Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f2a8-126">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>

<span data-ttu-id="7f2a8-127">Editor:</span><span class="sxs-lookup"><span data-stu-id="7f2a8-127">Editors:</span></span>

> <span data-ttu-id="7f2a8-128">**Maira Wenzel**, Sr. Content Developer, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7f2a8-128">**Maira Wenzel**, Sr. Content Developer, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="7f2a8-129">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="7f2a8-129">Who should use this guide</span></span>

<span data-ttu-id="7f2a8-130">I destinatari di questa guida sono principalmente sviluppatori, lead di sviluppo e architetti che sono interessati ad apprendere come creare applicazioni progettate per il cloud.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-130">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="7f2a8-131">Un pubblico secondario è costituito da Decision Maker tecnici che pianificano di scegliere se compilare le proprie applicazioni usando un approccio nativo per il cloud.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-131">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="7f2a8-132">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="7f2a8-132">How you can use this guide</span></span>

<span data-ttu-id="7f2a8-133">Questa guida inizia definendo cloud native e introducendo un'applicazione di riferimento compilata usando principi e tecnologie native del cloud.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-133">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="7f2a8-134">Oltre a questi primi due capitoli, il resto del libro è suddiviso in capitoli specifici che riguardano argomenti comuni alla maggior parte delle applicazioni native del cloud.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-134">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="7f2a8-135">È possibile passare a uno di questi capitoli per ottenere informazioni sugli approcci nativi del cloud per:</span><span class="sxs-lookup"><span data-stu-id="7f2a8-135">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="7f2a8-136">Accesso ai dati e ai dati</span><span class="sxs-lookup"><span data-stu-id="7f2a8-136">Data and data access</span></span>
- <span data-ttu-id="7f2a8-137">Modelli di comunicazione</span><span class="sxs-lookup"><span data-stu-id="7f2a8-137">Communication patterns</span></span>
- <span data-ttu-id="7f2a8-138">Scalabilità e scalabilità</span><span class="sxs-lookup"><span data-stu-id="7f2a8-138">Scaling and scalability</span></span>
- <span data-ttu-id="7f2a8-139">Resilienza delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="7f2a8-139">Application resiliency</span></span>
- <span data-ttu-id="7f2a8-140">Monitoraggio e integrità</span><span class="sxs-lookup"><span data-stu-id="7f2a8-140">Monitoring and health</span></span>
- <span data-ttu-id="7f2a8-141">Identità e sicurezza</span><span class="sxs-lookup"><span data-stu-id="7f2a8-141">Identity and security</span></span>
- <span data-ttu-id="7f2a8-142">DevOps</span><span class="sxs-lookup"><span data-stu-id="7f2a8-142">DevOps</span></span>

<span data-ttu-id="7f2a8-143">Questa guida è disponibile sia in formato PDF che in linea.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-143">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="7f2a8-144">È possibile inviare questo documento o collegamenti alla relativa versione online al team per garantire una conoscenza comune di questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-144">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="7f2a8-145">La maggior parte di questi argomenti trae vantaggio da una comprensione coerente dei principi e dei modelli sottostanti, nonché dei compromessi che interessano le decisioni correlate a questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-145">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="7f2a8-146">Il nostro obiettivo di questo documento è quello di dotare i team e i loro leader con le informazioni necessarie per prendere decisioni ben informate per l'architettura, lo sviluppo e l'hosting delle proprie applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7f2a8-146">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="7f2a8-147">avanti</span><span class="sxs-lookup"><span data-stu-id="7f2a8-147">Next</span></span>](introduction.md)
