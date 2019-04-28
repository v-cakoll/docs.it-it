---
title: F#Guida di stile
description: Informazioni sui cinque principi buone F# codice.
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61901849"
---
# <a name="f-style-guide"></a>F#Guida di stile

Gli articoli seguenti illustrano le linee guida per la formattazione di F# codice e le linee guida per le funzionalità del linguaggio e come devono essere usati.

Questo materiale sussidiario è stato formulato in base l'uso di F# di grandi dimensioni codebase con un gruppo di programmatori. Questo materiale sussidiario comporta in genere il corretto uso del F# e riduce al minimo delle proprie frustrazioni quando cambiano i requisiti per i programmi nel corso del tempo.

## <a name="five-principles-of-good-f-code"></a>Cinque principi buone F# codice

Infatti, i principi seguenti quando si scrive F# codice, soprattutto nei sistemi che cambia nel corso del tempo. Ciascun blocco di istruzioni in ulteriori articoli deriva da questi cinque punti.

1. **Valido F# è di codice conciso, espressivo e componibili**

    F#ha molte funzionalità che consentono di indicare le azioni in un minor numero di righe di codice e riutilizzare la funzionalità generica. Il F# libreria di base contiene anche numerosi tipi utili e funzioni per l'utilizzo di raccolte comuni dei dati. Composizione di funzioni personalizzate e quelli presenti il F# libreria di base (o altre librerie) sono una parte della routine idiomatico F# di programmazione. Come regola generale, se è possibile esprimere una soluzione a un problema in un minor numero di righe di codice, altri sviluppatori (o il self futuri) saranno apprezzabili. È anche consigliabile usare una libreria, ad esempio FSharp. core, il [vaste librerie .NET](../../../api/index.md) che F# viene eseguito, o un pacchetto di terze parti sul [NuGet](https://www.nuget.org/) quando è necessario eseguire un'operazione non semplice.

2. **Valido F# codice è interoperativo**

    L'interoperabilità può richiedere più forme, tra cui codice viene usato in linguaggi diversi. I limiti del codice di interoperabilità con altri chiamanti sono componenti critici per una corretta gestione, anche se i chiamanti inclusi in F#. Durante la scrittura di F#, si dovrebbe sempre pensare sul modo in cui altro codice chiamerà il codice che si sta scrivendo incluso se lo fanno si da un altro linguaggio, ad esempio C#. Il [ F# componente Design Guidelines](component-design-guidelines.md) descrivono l'interoperabilità in modo dettagliato.

3. **Valido F# codice rende usano programmazione degli oggetti, non dell'oggetto orientamento**

    F#include il supporto completo per la programmazione con gli oggetti in .NET, tra cui [classi](../language-reference/classes.md), [interfacce](../language-reference/interfaces.md), [modificatori di accesso](../language-reference/access-control.md), [classiastratte](../language-reference/abstract-classes.md)e così via. Per il codice funzionale più complesse, ad esempio le funzioni che devono essere sensibili al contesto, gli oggetti possono incapsulare facilmente informazioni contestuali in modi che non funzioni. Funzionalità, ad esempio [parametri facoltativi](../language-reference/members/methods.md#optional-arguments) e utilizzo accurato degli [overload](../language-reference/members/methods.md#overloaded-methods) può semplificare l'utilizzo di questa funzionalità per i chiamanti.

4. **Valido F# consente di eseguire codice anche senza esporre mutation**

    Non è un segreto per scrivere codice con prestazioni elevate, è necessario usare mutation. È come computer di lavoro, dopotutto. Tale codice è spesso difficile fare in modo corretto e soggetta a errori. Evitare di esporre mutation ai chiamanti. Al contrario, [creare un'interfaccia funzionale che consente di nascondere un'implementazione basata su mutation](conventions.md#performance) quando le prestazioni sono critiche.

5. **Valido F# codice è ricco di strumenti**

    Gli strumenti sono molto utili per lavorare in grandi codebase, ed è possibile scrivere F# scrivere il codice in modo che può essere utilizzato in modo più efficace con F# strumenti di linguaggio. Un esempio consiste nella verifica che non esagerare con uno stile privi di punti di programmazione, in modo che i valori intermedi possono essere controllati con un debugger. Un altro esempio consiste nell'usare [commenti in formato documentazione XML](../language-reference/xml-documentation.md) che descrivono costrutti in modo che le descrizioni comandi negli editor è possibile visualizzare tali commenti nel sito di chiamata. Sempre pensare a come il codice verrà letto, ci si sposta, eseguire il debug e modificato da altri programmatori con gli strumenti.

## <a name="next-steps"></a>Passaggi successivi

Il [ F# linee guida per la formattazione del codice](formatting.md) forniscono materiale sussidiario su come formattare il codice in modo che risulti facilmente leggibile.

Il [ F# convenzioni di codifica](conventions.md) forniscono materiale sussidiario per F# idiomi che consentono la manutenzione a lungo termine di dimensioni maggiori di programmazione F# basi di codice.

Il [ F# linee guida di progettazione componenti](component-design-guidelines.md) forniscono materiale sussidiario per la creazione di F# componenti, ad esempio le raccolte.
