---
title: Modernizzazione di app desktop in Windows 10 con .NET Core 3,1
description: Informazioni su come modernizzare le app desktop esistenti con .NET Core 3,1
ms.date: 05/12/2020
ms.openlocfilehash: 5861f806a9158ef761c47bc23e51327d4e2d0480
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83423236"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-core-31"></a><span data-ttu-id="63bfb-103">Modernizzazione di app desktop in Windows 10 con .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="63bfb-103">Modernizing Desktop Apps on Windows 10 with .NET Core 3.1</span></span>

![Screenshot che mostra la copertina e-book di modernizzare le app desktop.](./media/modernizing-existing-desktop-apps-ebook-cover.png)

<span data-ttu-id="63bfb-105">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="63bfb-105">PUBLISHED BY</span></span>

<span data-ttu-id="63bfb-106">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63bfb-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="63bfb-107">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="63bfb-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="63bfb-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="63bfb-108">One Microsoft Way</span></span>

<span data-ttu-id="63bfb-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="63bfb-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="63bfb-110">Copyright © 2020 di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="63bfb-110">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="63bfb-111">Tutti i diritti sono riservati.</span><span class="sxs-lookup"><span data-stu-id="63bfb-111">All rights reserved.</span></span> <span data-ttu-id="63bfb-112">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="63bfb-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="63bfb-113">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="63bfb-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="63bfb-114">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="63bfb-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="63bfb-115"> Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="63bfb-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="63bfb-116">Nessuna associazione reale o connessione è intenzionale o può essere desunta.</span><span class="sxs-lookup"><span data-stu-id="63bfb-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="63bfb-117">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="63bfb-117">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="63bfb-118">Mac e macOS sono marchi registrati di Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="63bfb-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="63bfb-119">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="63bfb-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="63bfb-120">Coautori:</span><span class="sxs-lookup"><span data-stu-id="63bfb-120">Co-Authors:</span></span>

> <span data-ttu-id="63bfb-121">**Olia gavrysh**, Program Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-121">**Olia Gavrysh**, Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="63bfb-122">**Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel</span><span class="sxs-lookup"><span data-stu-id="63bfb-122">**Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel</span></span>

<span data-ttu-id="63bfb-123">Collaboratori e revisori:</span><span class="sxs-lookup"><span data-stu-id="63bfb-123">Participants and reviewers:</span></span>

> <span data-ttu-id="63bfb-124">**Maira Wenzel**, Senior Program Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-124">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="63bfb-125">**Andy de Gorge**, sviluppatore di contenuti Senior, team di documentazione .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-125">**Andy De Gorge**, Senior Content Developer, .NET docs team, Microsoft</span></span>

> <span data-ttu-id="63bfb-126">**Miguel Ramos**, Senior Program Manager, team Windows Developer Platform, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-126">**Miguel Ramos**, Senior Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="63bfb-127">**Adam Braden**, responsabile programma principale, team Windows Developer Platform, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-127">**Adam Braden**, Principal Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="63bfb-128">**Ricardo minguez Pablos**, Senior Program Manager, team di Azure, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-128">**Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT team, Microsoft</span></span>

> <span data-ttu-id="63bfb-129">**Nitura Anil**, Senior Program Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-129">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="63bfb-130">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-130">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span></span>

> <span data-ttu-id="63bfb-131">**Scott Hunter**, responsabile del programma partner Director, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="63bfb-131">**Scott Hunter**, Partner Director Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="63bfb-132">**Marta Fuentes Lara**, Kabel</span><span class="sxs-lookup"><span data-stu-id="63bfb-132">**Marta Fuentes Lara**, Kabel</span></span>

> <span data-ttu-id="63bfb-133">**Raúl Fernández de Cordova**, Kabel</span><span class="sxs-lookup"><span data-stu-id="63bfb-133">**Raúl Fernández de Córdoba**, Kabel</span></span>

> <span data-ttu-id="63bfb-134">**Antonio Manuel Fernández Cantos**, Kabel</span><span class="sxs-lookup"><span data-stu-id="63bfb-134">**Antonio Manuel Fernández Cantos**, Kabel</span></span>

## <a name="introduction"></a><span data-ttu-id="63bfb-135">Introduzione</span><span class="sxs-lookup"><span data-stu-id="63bfb-135">Introduction</span></span>

<span data-ttu-id="63bfb-136">Questo libro riguarda le strategie che è possibile adottare per spostare le applicazioni desktop esistenti tramite il percorso di modernizzazione e incorporare le funzionalità più recenti di runtime, linguaggio e piattaforma.</span><span class="sxs-lookup"><span data-stu-id="63bfb-136">This book is about strategies you can adopt to move your existing desktop applications through the path of modernization and incorporate the latest runtime, language, and platform features.</span></span> <span data-ttu-id="63bfb-137">Si noterà che non esiste una ricetta univoca poiché ogni applicazione è diversa, quindi i requisiti e le preferenze.</span><span class="sxs-lookup"><span data-stu-id="63bfb-137">You'll discover that there's no unique recipe as each application is different, and so are your requirements and preferences.</span></span> <span data-ttu-id="63bfb-138">La novità è che esistono approcci comuni che è possibile applicare per aggiungere nuove funzionalità e funzionalità alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="63bfb-138">The good news is that there are common approaches you can apply to add new features and capabilities to your applications.</span></span> <span data-ttu-id="63bfb-139">Alcune di esse non richiedono anche modifiche sostanziali del codice.</span><span class="sxs-lookup"><span data-stu-id="63bfb-139">Some of them won't even require major modifications of your code.</span></span> <span data-ttu-id="63bfb-140">In questo libro viene illustrato il funzionamento di tutte le funzionalità dietro le quinte e viene illustrato il meccanismo delle loro implementazioni.</span><span class="sxs-lookup"><span data-stu-id="63bfb-140">In this book, we'll reveal how all those features work behind the scenes and explain the mechanics of their implementations.</span></span> <span data-ttu-id="63bfb-141">Sono inoltre disponibili alcuni scenari comuni per la modernizzazione delle applicazioni desktop esistenti illustrate in modo dettagliato, in modo da poter trovare l'ispirazione per l'evoluzione dei progetti.</span><span class="sxs-lookup"><span data-stu-id="63bfb-141">Moreover, you'll find some common scenarios for modernizing existing desktop applications shown in detail so you can find inspiration for evolving your projects.</span></span>

<span data-ttu-id="63bfb-142">L'approccio di Microsoft alla modernizzazione delle applicazioni esistenti è quello di offrire la flessibilità necessaria per creare un percorso personalizzato.</span><span class="sxs-lookup"><span data-stu-id="63bfb-142">Microsoft's approach to modernizing existing applications is to give you the flexibility to create your own customized path.</span></span> <span data-ttu-id="63bfb-143">Tutte le strategie di modernizzazione descritte in questo libro sono perlopiù indipendenti.</span><span class="sxs-lookup"><span data-stu-id="63bfb-143">All the modernization strategies described in this book are mostly independent.</span></span> <span data-ttu-id="63bfb-144">È possibile scegliere quelli rilevanti per l'applicazione e ignorare altri utenti che non sono importanti.</span><span class="sxs-lookup"><span data-stu-id="63bfb-144">You can choose ones that are relevant for your application and skip others that aren't important for you.</span></span> <span data-ttu-id="63bfb-145">In altre parole, è possibile combinare le strategie per soddisfare al meglio le esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="63bfb-145">In other words, you can mix and match the strategies to best address your application needs.</span></span>

## <a name="who-should-use-the-book"></a><span data-ttu-id="63bfb-146">Chi deve usare il libro</span><span class="sxs-lookup"><span data-stu-id="63bfb-146">Who should use the book</span></span>

<span data-ttu-id="63bfb-147">Questo libro è stato scritto per sviluppatori e architetti di soluzioni che vogliono modernizzare le applicazioni di Windows Forms e desktop WPF esistenti per sfruttare i vantaggi di .NET Core e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="63bfb-147">We wrote this book for developers and solution architects who want to modernize existing Windows Forms and WPF desktop applications to leverage the benefits of .NET Core and Windows 10.</span></span>

<span data-ttu-id="63bfb-148">Questo libro può essere utile anche se si è un decisore tecnico, ad esempio un progettista aziendale o un responsabile dello sviluppo o un direttore che desidera una panoramica dei vantaggi dell'aggiornamento delle applicazioni desktop esistenti.</span><span class="sxs-lookup"><span data-stu-id="63bfb-148">You might also find this book useful if you're a technical decision maker, such as an enterprise architect or a development lead or director who wants an overview of the benefits of updating existing desktop applications.</span></span>

## <a name="how-to-use-the-book"></a><span data-ttu-id="63bfb-149">Come usare il libro</span><span class="sxs-lookup"><span data-stu-id="63bfb-149">How to use the book</span></span>

<span data-ttu-id="63bfb-150">Questo libro illustra il motivo per cui è consigliabile modernizzare le applicazioni esistenti e i vantaggi specifici offerti dall'uso di NET Core 3,1 e MSIX per modernizzare le app desktop.</span><span class="sxs-lookup"><span data-stu-id="63bfb-150">This book addresses the "why"—why you might want to modernize your existing applications, and the specific benefits you get from using NET Core 3.1 and MSIX to modernize your desktop apps.</span></span> <span data-ttu-id="63bfb-151">Il contenuto del libro è progettato per architetti e responsabili decisionali tecnici che vogliono una panoramica, ma che non devono concentrarsi sull'implementazione e i dettagli tecnici.</span><span class="sxs-lookup"><span data-stu-id="63bfb-151">The content of the book is designed for architects and technical decision makers who want an overview, but who don't need to focus on implementation and technical, step-by-step details.</span></span>

<span data-ttu-id="63bfb-152">Insieme ai diversi capitoli, vengono forniti frammenti di codice e schermate di implementazione di esempio, con il capitolo 5 dedicato alla presentazione di un processo di migrazione completo per le applicazioni di esempio.</span><span class="sxs-lookup"><span data-stu-id="63bfb-152">Along the different chapters, sample implementation code snippets and screenshots are provided, with chapter 5 devoted to showcase a complete migration process for sample applications.</span></span>

## <a name="what-this-book-doesnt-cover"></a><span data-ttu-id="63bfb-153">Argomenti non coperti da questo libro</span><span class="sxs-lookup"><span data-stu-id="63bfb-153">What this book doesn't cover</span></span>

<span data-ttu-id="63bfb-154">In questo libro viene trattato un subset specifico di scenari focalizzati sugli scenari di Lift-and-Shift, che delineano il modo in cui ottenere i vantaggi della modernizzazione senza la necessità di riscrivere il codice.</span><span class="sxs-lookup"><span data-stu-id="63bfb-154">This book covers a specific subset of scenarios that are focused on lift-and-shift scenarios, outlining the way to gain the benefits of modernizing without the effort of rewriting code.</span></span>

<span data-ttu-id="63bfb-155">Questo libro non riguarda lo sviluppo di applicazioni moderne con .NET Core da zero o informazioni introduttive su Windows Forms e WPF.</span><span class="sxs-lookup"><span data-stu-id="63bfb-155">This book isn't about developing modern applications with .NET Core from scratch or about getting started with Windows Forms and WPF.</span></span> <span data-ttu-id="63bfb-156">Questo argomento è incentrato sul modo in cui è possibile aggiornare le applicazioni desktop esistenti con le tecnologie più recenti per lo sviluppo desktop.</span><span class="sxs-lookup"><span data-stu-id="63bfb-156">It focuses on how you can update existing desktop applications with the latest technologies for desktop development.</span></span>

## <a name="samples-used-in-this-book"></a><span data-ttu-id="63bfb-157">Esempi utilizzati in questo libro</span><span class="sxs-lookup"><span data-stu-id="63bfb-157">Samples used in this book</span></span>

<span data-ttu-id="63bfb-158">Per evidenziare i passaggi necessari per eseguire una modernizzazione, verrà usata un'applicazione di esempio denominata `eShopModernizing` .</span><span class="sxs-lookup"><span data-stu-id="63bfb-158">To highlight the necessary steps to perform a modernization, we'll be using a sample application called `eShopModernizing`.</span></span> <span data-ttu-id="63bfb-159">Questa applicazione dispone di due versioni, Windows Forms e WPF, e verrà illustrata una procedura dettagliata su come eseguire la modernizzazione in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="63bfb-159">This application has two flavors, Windows Forms and WPF, and we'll show a step-by-step process on how to perform the modernization on both of them to .NET Core.</span></span>

<span data-ttu-id="63bfb-160">Inoltre, nel repository GitHub per questo libro, si troveranno i risultati del processo, che è possibile consultare se si decide di seguire l'esercitazione dettagliata.</span><span class="sxs-lookup"><span data-stu-id="63bfb-160">Also, on the GitHub repository for this book, you'll find the results of the process, which you can consult with if you decide to follow the step-by-step tutorial.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="63bfb-161">Invia commenti e suggerimenti</span><span class="sxs-lookup"><span data-stu-id="63bfb-161">Send your feedback</span></span>

<span data-ttu-id="63bfb-162">Questo libro ed esempi correlati sono in continua evoluzione, quindi il feedback è stato accolto.</span><span class="sxs-lookup"><span data-stu-id="63bfb-162">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="63bfb-163">Per Commenti su come migliorare questo libro, usare la sezione feedback nella parte inferiore di qualsiasi pagina basata su [problemi di GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="63bfb-163">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="63bfb-164">Avanti</span><span class="sxs-lookup"><span data-stu-id="63bfb-164">Next</span></span>](why-modern-applications.md)
