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
# <a name="modernizing-desktop-apps-on-windows-10-with-net-core-31"></a>Modernizzazione di app desktop in Windows 10 con .NET Core 3,1

![Screenshot che mostra la copertina e-book di modernizzare le app desktop.](./media/modernizing-existing-desktop-apps-ebook-cover.png)

PUBBLICATO DA

Microsoft Developer Division, team dei prodotti .NET e Visual Studio

Una divisione di Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2020 di Microsoft Corporation

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

 Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi. Nessuna associazione reale o connessione è intenzionale o può essere desunta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.

Mac e macOS sono marchi registrati di Apple Inc.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Coautori:

> **Olia gavrysh**, Program Manager, team di .NET, Microsoft

> **Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel

Collaboratori e revisori:

> **Maira Wenzel**, Senior Program Manager, team di .NET, Microsoft

> **Andy de Gorge**, sviluppatore di contenuti Senior, team di documentazione .NET, Microsoft

> **Miguel Ramos**, Senior Program Manager, team Windows Developer Platform, Microsoft

> **Adam Braden**, responsabile programma principale, team Windows Developer Platform, Microsoft

> **Ricardo minguez Pablos**, Senior Program Manager, team di Azure, Microsoft

> **Nitura Anil**, Senior Program Manager, team di .NET, Microsoft

> **Beth Massi**, Senior Product Marketing Manager, Microsoft

> **Scott Hunter**, responsabile del programma partner Director, team di .NET, Microsoft

> **Marta Fuentes Lara**, Kabel

> **Raúl Fernández de Cordova**, Kabel

> **Antonio Manuel Fernández Cantos**, Kabel

## <a name="introduction"></a>Introduzione

Questo libro riguarda le strategie che è possibile adottare per spostare le applicazioni desktop esistenti tramite il percorso di modernizzazione e incorporare le funzionalità più recenti di runtime, linguaggio e piattaforma. Si noterà che non esiste una ricetta univoca poiché ogni applicazione è diversa, quindi i requisiti e le preferenze. La novità è che esistono approcci comuni che è possibile applicare per aggiungere nuove funzionalità e funzionalità alle applicazioni. Alcune di esse non richiedono anche modifiche sostanziali del codice. In questo libro viene illustrato il funzionamento di tutte le funzionalità dietro le quinte e viene illustrato il meccanismo delle loro implementazioni. Sono inoltre disponibili alcuni scenari comuni per la modernizzazione delle applicazioni desktop esistenti illustrate in modo dettagliato, in modo da poter trovare l'ispirazione per l'evoluzione dei progetti.

L'approccio di Microsoft alla modernizzazione delle applicazioni esistenti è quello di offrire la flessibilità necessaria per creare un percorso personalizzato. Tutte le strategie di modernizzazione descritte in questo libro sono perlopiù indipendenti. È possibile scegliere quelli rilevanti per l'applicazione e ignorare altri utenti che non sono importanti. In altre parole, è possibile combinare le strategie per soddisfare al meglio le esigenze dell'applicazione.

## <a name="who-should-use-the-book"></a>Chi deve usare il libro

Questo libro è stato scritto per sviluppatori e architetti di soluzioni che vogliono modernizzare le applicazioni di Windows Forms e desktop WPF esistenti per sfruttare i vantaggi di .NET Core e Windows 10.

Questo libro può essere utile anche se si è un decisore tecnico, ad esempio un progettista aziendale o un responsabile dello sviluppo o un direttore che desidera una panoramica dei vantaggi dell'aggiornamento delle applicazioni desktop esistenti.

## <a name="how-to-use-the-book"></a>Come usare il libro

Questo libro illustra il motivo per cui è consigliabile modernizzare le applicazioni esistenti e i vantaggi specifici offerti dall'uso di NET Core 3,1 e MSIX per modernizzare le app desktop. Il contenuto del libro è progettato per architetti e responsabili decisionali tecnici che vogliono una panoramica, ma che non devono concentrarsi sull'implementazione e i dettagli tecnici.

Insieme ai diversi capitoli, vengono forniti frammenti di codice e schermate di implementazione di esempio, con il capitolo 5 dedicato alla presentazione di un processo di migrazione completo per le applicazioni di esempio.

## <a name="what-this-book-doesnt-cover"></a>Argomenti non coperti da questo libro

In questo libro viene trattato un subset specifico di scenari focalizzati sugli scenari di Lift-and-Shift, che delineano il modo in cui ottenere i vantaggi della modernizzazione senza la necessità di riscrivere il codice.

Questo libro non riguarda lo sviluppo di applicazioni moderne con .NET Core da zero o informazioni introduttive su Windows Forms e WPF. Questo argomento è incentrato sul modo in cui è possibile aggiornare le applicazioni desktop esistenti con le tecnologie più recenti per lo sviluppo desktop.

## <a name="samples-used-in-this-book"></a>Esempi utilizzati in questo libro

Per evidenziare i passaggi necessari per eseguire una modernizzazione, verrà usata un'applicazione di esempio denominata `eShopModernizing` . Questa applicazione dispone di due versioni, Windows Forms e WPF, e verrà illustrata una procedura dettagliata su come eseguire la modernizzazione in .NET Core.

Inoltre, nel repository GitHub per questo libro, si troveranno i risultati del processo, che è possibile consultare se si decide di seguire l'esercitazione dettagliata.

## <a name="send-your-feedback"></a>Invia commenti e suggerimenti

Questo libro ed esempi correlati sono in continua evoluzione, quindi il feedback è stato accolto. Per Commenti su come migliorare questo libro, usare la sezione feedback nella parte inferiore di qualsiasi pagina basata su [problemi di GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Avanti](why-modern-applications.md)
