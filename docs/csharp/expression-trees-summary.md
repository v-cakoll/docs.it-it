---
title: Riepilogo degli alberi delle espressioni
description: Viene riepilogato come usare gli alberi delle espressioni per creare programmi dinamici che interpretano il codice sotto forma di dati e creare nuove funzionalità basate su tale codice.
ms.date: 06/20/2016
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.openlocfilehash: e0d46aa67b61fd4e1d2bcc20b4a567524bb00301
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="expression-trees-summary"></a>Riepilogo degli alberi delle espressioni

[Precedente -- Traduzione delle espressioni](expression-trees-translating.md)

In questa serie, abbiamo visto come usare gli *alberi delle espressioni* per creare programmi dinamici che interpretano il codice sotto forma di dati e come compilare nuove funzionalità basate su tale codice.

È possibile esaminare gli alberi delle espressioni per comprendere lo scopo di un algoritmo e non solo il codice. È possibile compilare nuovi alberi delle espressioni che rappresentano le versioni modificate del codice originale.

È anche possibile usare gli alberi delle espressioni per esaminare un algoritmo e convertirlo in un altro linguaggio o ambiente. 

## <a name="limitations"></a>Limitazioni

Esistono alcuni elementi del linguaggio C# più recenti per cui la traslazione in alberi delle espressioni non funziona bene. Gli alberi delle espressioni non possono contenere espressioni `await` o espressioni lambda `async`. Molte delle funzionalità aggiunte nella versione C# 6 non vengono visualizzate esattamente come scritte negli alberi delle espressioni. Al contrario, le funzionalità più recenti verranno esposte negli alberi delle espressioni nell'equivalente sintassi precedente. Ciò potrebbe non costituire una limitazione come si potrebbe pensare. Questo significa che il codice che interpreta gli alberi delle espressioni continuerà probabilmente a funzionare quando verranno introdotte nuove funzionalità del linguaggio.

Nonostante queste limitazioni, gli alberi delle espressioni consentono di creare algoritmi dinamici che si basano sull'interpretazione e sulla modifica del codice rappresentato come struttura di dati. È uno strumento potente e rappresenta una delle funzionalità dell'ecosistema .NET che consente alle librerie avanzate come Entity Framework di portare a termine le operazioni previste.

