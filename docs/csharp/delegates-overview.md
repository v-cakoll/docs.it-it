---
title: Introduzione ai delegati
description: Questo argomento di panoramica fornisce informazioni sui delegati presentando i concetti di base e descrivendo gli obiettivi di progettazione del linguaggio per i delegati.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 59b61d77-84e5-457b-8da5-fb5f24ca6ed6
ms.openlocfilehash: fd594f77c034533a1d5aee1d8279e9b727284311
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146229"
---
# <a name="introduction-to-delegates"></a>Introduzione ai delegati

I delegati offrono un meccanismo di *associazione tardiva* in .NET. L'associazione tardiva indica la creazione di un algoritmo in cui il chiamante specifica almeno un metodo che implementa parte dell'algoritmo.

Ad esempio, si consideri l'ordinamento di un elenco di stelle in un'applicazione di astronomia.
È possibile scegliere di ordinare le stelle in base alla distanza da terra, alla grandezza o alla luminosità percepita.

In tutti i casi, il metodo Sort() esegue essenzialmente la stessa operazione, ovvero ordina gli elementi nell'elenco in base a un confronto. Il codice che esegue il confronto di due stelle è diverso per ognuno degli ordinamenti.

Questi tipi di soluzioni sono stati usati nel software per mezzo secolo.
Il concetto di delegato del linguaggio C# offre un supporto del linguaggio di prima classe e indipendenza dai tipi.

Come descritto più avanti, il codice C# scritto per questo tipo di algoritmi è indipendente dai tipi e usa il linguaggio e il compilatore per verificare che i tipi corrispondano per gli argomenti e i tipi restituiti.

## <a name="language-design-goals-for-delegates"></a>Obiettivi della progettazione del linguaggio per i delegati

I designer del linguaggio hanno enumerato diversi obiettivi per la funzionalità che in seguito è diventata la funzionalità dei delegati.

Il team voleva un costrutto di linguaggio comune che potesse essere usato per i successivi algoritmi di associazione tardiva. Ciò consente agli sviluppatori di apprendere un solo concetto e di usare lo stesso concetto in diversi problemi software.

In secondo luogo, il team voleva supportare le chiamate al metodo sia singole che multicast. I delegati multicast sono i delegati che concatenano più chiamate al metodo.
Alcuni esempi sono disponibili [più avanti in questa serie](delegate-class.md).

Il team voleva che i delegati supportassero la stessa indipendenza dai tipi stesso che gli sviluppatori si aspettano da tutti i costrutti C#.

Infine il team ha riconosciuto che un modello di evento è un modello specifico, in cui i delegati o qualsiasi algoritmo di associazione tardiva risultano molto utili. Il team voleva assicurarsi che il codice per i delegati potesse offrire la base per il modello di evento di .NET.

Il risultato di tutto il lavoro sono stati il delegato e il supporto degli eventi di C# e .NET. Gli articoli rimanenti di questa sezione descrivono le funzionalità del linguaggio, il supporto delle librerie e i termini comuni usati per i delegati.

Verranno fornite informazioni sulla parola chiave `delegate` e sul codice generato dalla parola chiave. Verranno fornite informazioni sulle funzionalità nella classe `System.Delegate` e sul loro utilizzo. Si apprenderà come creare delegati indipendenti dai tipi e come creare metodi che possono essere richiamati tramite i delegati. Si apprenderà anche come usare i delegati e gli eventi tramite le espressioni lambda. Sarà possibile osservare il punto nel quale i delegati diventano uno dei blocchi predefiniti per LINQ. Si apprenderà come delegati costituiscono la base per lo schema di eventi .NET e come sono diversi.

In generale, sarà possibile osservare in che modo i delegati sono parte integrante della programmazione in .NET e dell'uso con le API del framework.

È ora possibile iniziare.

[Avanti](delegate-class.md)
