---
title: 'Guida di stile di F #'
description: 'Altre cinque principi di codice F # funzionante.'
ms.date: 05/14/2018
ms.openlocfilehash: 6d8c1336ca991040a8f6e13290d209cb3b70054d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
---
# <a name="f-style-guide"></a>Guida di stile di F #

Gli articoli seguenti descrivono linee guida per la formattazione di codice F # e topica materiale sussidiario per la funzionalità del linguaggio e come deve essere utilizzati.

Questa guida è stata formulata in base alle basi di codice l'utilizzo di F # in grandi dimensioni con un gruppo di programmatori. Questo materiale sussidiario in genere comporta un utilizzo corretto di F # e riduce al minimo proprie frustrazioni quando cambiano i requisiti per i programmi nel corso del tempo.

## <a name="five-principles-of-good-f-code"></a>Cinque principi di buona codice F #

È consigliabile mantenere i principi seguenti in considerazione quando che si scrive codice F #, in particolare nei sistemi che cambiano nel corso del tempo. Ogni parte del materiale sussidiario negli articoli ulteriormente scaturito da queste cinque punti.

1. **Buona codice F # è ridotte ed espressive**

    F # offre numerose funzionalità che consentono di esprimere le azioni in un minor numero di righe di codice e riutilizzare funzionalità generica. La libreria di base F # contiene inoltre numerosi tipi utili e funzioni per l'utilizzo di raccolte comuni dei dati. Come regola generale, se è possibile esprimere una soluzione per risolvere un problema in un minor numero di righe di codice, altri sviluppatori (o se stesso futuro) sarà apprezzabili. È inoltre consigliabile utilizzare una libreria, ad esempio FSharp. core, il [librerie .NET vast](https://docs.microsoft.com/dotnet/api/) che F # viene eseguita, o un pacchetto di terze parti sul [NuGet](https://www.nuget.org/) quando è necessario eseguire un'operazione non semplice.

2. **Buona codice F # è interoperativo**

    L'interoperabilità può avere più forme, inclusi l'utilizzo di codice in linguaggi diversi. I limiti del codice di interoperabilità con altri chiamanti sono parti importanti predisporre correttamente. Durante la scrittura di F #, si deve sempre pensare sul modo in cui altri codice chiamerà il codice in cui che si sta scrivendo, inclusi se a tale scopo da un altro linguaggio come c#. Il [F # componente linee guida di progettazione](component-design-guidelines.md) descrivono interoperabilità in modo dettagliato.

3. **Buona codice F # rende utilizzare della programmazione di oggetti, non oggetti orientamento**

    F # contiene il supporto completo per la programmazione con gli oggetti in .NET, tra cui [classi](../language-reference/classes.md), [interfacce](../language-reference/interfaces.md), [modificatori di accesso](../language-reference/access-control.md), [classiastratte](../language-reference/abstract-classes.md)e così via. Per il codice funzionale più complessi, ad esempio le funzioni che è necessario che riconoscano il contesto, oggetti possono incapsulare facilmente le informazioni contestuali in modo tale che non funzioni. Funzionalità, ad esempio [parametri facoltativi](../language-reference/members/methods.md#optional-arguments) e [overload](../language-reference/members/methods.md#overloaded-methods) semplificano inoltre l'utilizzo di questa funzionalità per i chiamanti.

4. **Buona codice F # esegue anche senza esporre mutazione**

    Non è un segreto per scrivere il codice ad alte prestazioni, è necessario utilizzare mutazione. È come computer di lavoro, dopo che tutti. Tale codice è spesso difficile predisporre e soggetta a errori. Evitare di esporre mutazione ai chiamanti. Cercare un'interfaccia funzionale tramite un'implementazione basata su mutazione.

5. **Buona codice F # è ricco**

    Gli strumenti sono estremamente utili per l'utilizzo di grandi dimensioni codebase, è possibile scrivere codice F # in modo che può essere utilizzato in modo più efficace con gli strumenti di linguaggio F #. Un esempio consiste nell'assicurarsi che non esagerare con uno stile senza punto di programmazione, in modo che i valori intermedi possono essere controllati con un debugger. Un altro esempio è utilizzando [commenti della documentazione XML](../language-reference/xml-documentation.md) che descrivono i costrutti in modo che le descrizioni comandi negli editor è possibile visualizzare i commenti nel sito di chiamata. Valutare sempre come codice verrà letti, ci si sposta, eseguire il debug e modificato da altri programmatori con i propri strumenti.

## <a name="next-steps"></a>Passaggi successivi

Il [codice F # la formattazione di linee guida](formatting.md) vengono fornite indicazioni sulle modalità di formattazione di codice in modo che sia facile da leggere.

Il [F # convenzioni di codifica](conventions.md) forniscono materiale sussidiario per idiomi utili per la manutenzione a lungo termine di dimensioni maggiori F # di programmazione F # basi di codice.

Il [F # componente linee guida di progettazione](component-design-guidelines.md) forniscono materiale sussidiario per la creazione di componenti di F #, ad esempio le raccolte.
