---
title: 'Guida di stile per F #'
description: 'Informazioni sui cinque principi del buon codice F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 6d8c1336ca991040a8f6e13290d209cb3b70054d
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2018
ms.locfileid: "34235905"
---
# <a name="f-style-guide"></a>Guida di stile per F #

Gli articoli seguenti illustrano le linee guida per la formattazione del codice F # e le linee guida per le funzionalità del linguaggio e come devono essere usati.

Questa guida è stata formulata in base l'utilizzo di F # in grandi codebase con un gruppo di programmatori. Questo materiale sussidiario in genere comporta il corretto utilizzo di F # e riduce al minimo delle proprie frustrazioni quando cambiano i requisiti per i programmi nel corso del tempo.

## <a name="five-principles-of-good-f-code"></a>Cinque principi del buon codice F #

È consigliabile tenere i principi seguenti presenti quando che si scrive codice F #, soprattutto nei sistemi che cambiano nel corso del tempo. Ciascun blocco di istruzioni in ulteriori articoli deriva da questi cinque punti.

1. **Buon codice F # è concisa ed espressivo**

    F # offre molte funzionalità che consentono di indicare le azioni in un minor numero di righe di codice e riutilizzare la funzionalità generica. Libreria di base F # contiene inoltre numerosi tipi utili e funzioni per l'utilizzo di raccolte comuni dei dati. Come regola generale, se è possibile esprimere una soluzione a un problema in un minor numero di righe di codice, altri sviluppatori (o il self futuri) saranno apprezzabili. È anche consigliabile usare una libreria, ad esempio FSharp. core, il [librerie .NET vaste](https://docs.microsoft.com/dotnet/api/) che F # viene eseguito, o un pacchetto di terze parti in [NuGet](https://www.nuget.org/) quando è necessario eseguire un'operazione non semplice.

2. **Buon codice F # è interoperativo**

    L'interoperabilità può richiedere più forme, tra cui codice viene usato in linguaggi diversi. I limiti del codice di interoperabilità con altri chiamanti sono componenti critici per ottenere i diritti. Quando si scrive in F #, si dovrebbe sempre pensare sul modo in cui altro codice chiamerà il codice per scrivere, tra cui se lo fanno si da un altro linguaggio come c#. Il [F # componente Design Guidelines](component-design-guidelines.md) descrivono l'interoperabilità in modo dettagliato.

3. **Buon codice F # rende usano programmazione degli oggetti, non dell'oggetto orientamento**

    F # offre supporto completo per la programmazione con gli oggetti in .NET, tra cui [classi](../language-reference/classes.md), [interfacce](../language-reference/interfaces.md), [modificatori di accesso](../language-reference/access-control.md), [classiastratte](../language-reference/abstract-classes.md)e così via. Per il codice funzionale più complesse, ad esempio le funzioni che devono essere sensibili al contesto, gli oggetti possono incapsulare facilmente informazioni contestuali in modi che non funzioni. Funzionalità, ad esempio [parametri facoltativi](../language-reference/members/methods.md#optional-arguments) e utilizzo accurato degli [overload](../language-reference/members/methods.md#overloaded-methods) può semplificare l'utilizzo di questa funzionalità per i chiamanti.

4. **Buon codice F # esegue anche senza esporre mutation**

    Non è un segreto per scrivere codice con prestazioni elevate, è necessario usare mutation. È come computer di lavoro, dopotutto. Tale codice è spesso difficile fare in modo corretto e soggetta a errori. Evitare di esporre mutation ai chiamanti. Al contrario, [creare un'interfaccia funzionale che consente di nascondere un'implementazione basata su mutation](conventions.md#performance) quando le prestazioni sono critiche.

5. **Buon codice F # è ricco di strumenti**

    Gli strumenti sono molto utili per lavorare in grandi codebase, ed è possibile scrivere codice F # in modo che può essere utilizzato in modo più efficace con strumenti di linguaggio F #. Un esempio consiste nella verifica che non esagerare con uno stile privi di punti di programmazione, in modo che i valori intermedi possono essere controllati con un debugger. Un altro esempio consiste nell'usare [commenti in formato documentazione XML](../language-reference/xml-documentation.md) che descrivono costrutti in modo che le descrizioni comandi negli editor è possibile visualizzare tali commenti nel sito di chiamata. Sempre pensare a come il codice verrà letto, ci si sposta, eseguire il debug e modificato da altri programmatori con gli strumenti.

## <a name="next-steps"></a>Passaggi successivi

Il [linee guida per la formattazione del codice F #](formatting.md) forniscono materiale sussidiario su come formattare il codice in modo che risulti facilmente leggibile.

Il [convenzioni di scrittura codice F #](conventions.md) forniscono materiale sussidiario per le codebase che consentono la manutenzione a lungo termine di dimensioni maggiori di F # linguaggi di programmazione F #.

Il [indicazioni per la progettazione di componente F #](component-design-guidelines.md) forniscono indicazioni per la creazione di componenti di F #, ad esempio le raccolte.
