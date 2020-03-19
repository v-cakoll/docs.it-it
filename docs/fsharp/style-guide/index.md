---
title: Guida di stile di F#
description: Informazioni sui cinque principi del buon codice F.
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400267"
---
# <a name="f-style-guide"></a>Guida di stile di F#

Negli articoli seguenti vengono descritte le linee guida per la formattazione del codice F e le indicazioni di argomento per le funzionalità del linguaggio e le relative modalità di utilizzo.

Queste linee guida sono state formulate in base all'uso di F in codebase di grandi dimensioni con un gruppo eterogeneo di programmatori. Queste linee guida in genere portano a un utilizzo efficace di F e riduce al minimo le frustrazioni quando i requisiti per i programmi cambiano nel tempo.

## <a name="five-principles-of-good-f-code"></a>Cinque principi di buon codice F

Tenere presenti i seguenti principi ogni volta che si scrive il codice F , in particolare nei sistemi che cambieranno nel tempo. Ogni atto di orientamento in altri articoli deriva da questi cinque punti.

1. **Il buon codice F è conciso, espressivo e componibile**

    F è dotato di molte funzionalità che consentono di esprimere azioni in un numero inferiore di righe di codice e riutilizzare le funzionalità generiche. La libreria di base di F , inoltre, contiene molti tipi utili e funzioni per l'utilizzo di raccolte comuni di dati. La composizione delle proprie funzioni e quelle nella libreria di base di F , o in altre librerie, fa parte della programmazione idiomatica di routine di F. Come regola generale, se è possibile esprimere una soluzione a un problema in un numero inferiore di righe di codice, altri sviluppatori (o il vostro futuro sé) sarà apprezzabile. Si consiglia inoltre di utilizzare una libreria, ad esempio FSharp.Core, le [vaste librerie .NET](../../../api/index.md) in cui viene eseguito F , o un pacchetto di terze parti su [NuGet](https://www.nuget.org/) quando è necessario eseguire un'attività non banale.

2. **Il codice Good F è interoperabile**

    L'interoperabilità può assumere più forme, incluso l'utilizzo di codice in linguaggi diversi. I limiti del codice con cui interagiscono altri chiamanti sono parti critiche per ottenere il corretto, anche se i chiamanti sono anche in F. Quando si scrive F, si dovrebbe sempre pensare a come altro codice chiamerà nel codice che si sta scrivendo, anche se lo fanno da un altro linguaggio come C . Le linee guida per la [progettazione](component-design-guidelines.md) dei componenti di F , descrivono l'interoperabilità in dettaglio.

3. **Il buon codice F , utilizza la programmazione a oggetti, non l'orientamento degli oggetti**

    In Fè è il supporto completo per la programmazione con oggetti in .NET, tra cui [classi,](../language-reference/classes.md) [interfacce,](../language-reference/interfaces.md)modificatori di [accesso,](../language-reference/access-control.md) [classi astratte](../language-reference/abstract-classes.md)e così via. Per codice funzionale più complesso, ad esempio funzioni che devono essere in grado di riconoscere il contesto, gli oggetti possono incapsulare facilmente le informazioni contestuali in modi che le funzioni non possono. Funzionalità quali [i parametri facoltativi](../language-reference/members/methods.md#optional-arguments) e un uso attento dell'overload possono [semplificare](../language-reference/members/methods.md#overloaded-methods) l'utilizzo di questa funzionalità per i chiamanti.

4. **Buon codice F , prestazioni buone senza esporre la mutazione**

    Non è un segreto che per scrivere codice ad alte prestazioni, è necessario utilizzare mutazione. È così che funzionano i computer, dopo tutto. Tale codice è spesso soggetto a errori e difficile da ottenere a destra. Evitare di esporre la mutazione ai chiamanti. Creare invece [un'interfaccia funzionale che nasconde un'implementazione basata sulla mutazione](conventions.md#performance) quando le prestazioni sono critiche.

5. **Il buon codice F è utilizzabile**

    Gli strumenti sono inestimabili per l'utilizzo in codebase di grandi dimensioni ed è possibile scrivere codice F , in modo che possa essere utilizzato in modo più efficace con gli strumenti del linguaggio F . Un esempio è assicurarsi di non esagetare con uno stile di programmazione senza punti, in modo che i valori intermedi possano essere esaminati con un debugger. Un altro esempio è l'utilizzo di [commenti della documentazione XML](../language-reference/xml-documentation.md) che descrivono i costrutti in modo che le descrizioni comandi negli editor possano visualizzare tali commenti nel sito di chiamata. Pensate sempre a come il codice verrà letto, esplorato, sottoposto a debug e manipolato da altri programmatori con i loro strumenti.

## <a name="next-steps"></a>Passaggi successivi

Le linee guida per [la formattazione](formatting.md) del codice F , forniscono indicazioni su come formattare il codice in modo che sia facile da leggere.

Le [convenzioni](conventions.md) di codifica F , forniscono indicazioni per idiomi di programmazione F , che consentono la manutenzione a lungo termine di basi di codice F .

Le linee guida per la [progettazione](component-design-guidelines.md) di componenti F , forniscono indicazioni per la creazione di componenti F , ad esempio le librerie.
