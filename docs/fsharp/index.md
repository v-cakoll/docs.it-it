---
title: Guida a F#
description: 'Questa guida fornisce una panoramica delle varie materiali di formazione per F #, un linguaggio di programmazione funzionale che viene eseguita su .NET.'
author: jackfoxy
ms.author: phcart
ms.date: 03/19/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 9c03148d42f3cf8731580e36990aa21c68f705f6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="f-guide"></a>Guida a F#

F # è un linguaggio di programmazione funzionale che viene eseguita su .NET. Include anche il supporto completo per gli oggetti, consentendo di blend funzionale e programmazione di oggetti pragmatic per soluzioni relative ai problemi.

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

F # è incentrato sulla produttività essenzialmente. Il supporto per gli strumenti per F # è universale e completo di funzionalità avanzate.

## <a name="learning-f"></a>Apprendimento F # #

[Presentazione di F #](tour.md) offra una panoramica delle funzionalità del linguaggio principale con un numero elevato di esempi di codice. Ciò è consigliabile se si ha familiarità con F # e si desidera ottenere un'idea di come funziona la lingua.

[Introduzione a F # in Visual Studio](get-started/get-started-visual-studio.md) se si sta in Windows e si desidera che l'IDE di Visual Studio (Integraded Development Environment) completa.

[Introduzione a F # in Visual Studio per Mac](get-started/get-started-with-visual-studio-for-mac.md) se è attiva su macOS e si desidera utilizzare un IDE di Visual Studio.

[Introduzione a F # in Visual Studio Code](get-started/get-started-vscode.md) se si desidera che un tipo semplice, multipiattaforma e completo di funzionalità IDE verificarsi.

[Introduzione a F # con l'interfaccia CLI Core .NET](get-started/get-started-command-line.md) se si desidera utilizzare gli strumenti da riga di comando.

[Introduzione a F # e Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) per la programmazione per dispositivi mobili con F #.

## <a name="references"></a>Riferimenti

[Riferimenti al linguaggio F #](language-reference/index.md) è il riferimento ufficiale e completo per tutte le funzionalità del linguaggio F #. Ogni articolo viene illustrata la sintassi e vengono mostrati esempi di codice. È possibile utilizzare la barra dei filtri nel sommario per trovare articoli specifici.

[Riferimenti alla libreria dei componenti di base F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) è il riferimento all'API per la libreria di base F #.


## <a name="additional-guides"></a>Guide aggiuntive

[F # per divertenti ed profitto](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) è un libro molto dettagliato sull'apprendimento F #. Il contenuto e l'autore sono amate dalla community di F #. Gli utenti di destinazione sono principalmente gli sviluppatori con uno sfondo di programmazione orientata agli oggetti.

[Wikibook di programmazione F #](https://en.wikibooks.org/wiki/F_Sharp_Programming) è un wikibook imparare F #. È inoltre un prodotto della community di F #. Gli utenti di destinazione sono chi ha familiarità con F #, con un po' di nozioni di programmazione orientata agli oggetti.

## <a name="learn-f-through-videos"></a>Informazioni su F # attraverso video

[Esercitazione su F # su YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) è un'ottima presentazione di F # con Visual Studio, che mostra un numero elevato di ottimi esempi che illustrano nel corso di 1,5 ore. Gli utenti di destinazione sono agli sviluppatori di Visual Studio che non hanno familiarità a F #.

[Introduzione alla programmazione con F #](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) è una serie di video grande che usa codice di Visual Studio come editor principale. La serie di video inizia da zero e termina con la creazione di un gioco di video RPG basata su testo. I destinatari di destinazione sono gli sviluppatori preferiscono Visual Studio Code (o un IDE lightweight) e non si conosce a F #.

[Novità in Visual Studio 2017 per F # per gli sviluppatori](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) un corso video che illustra alcune delle funzionalità più recenti per F # in Visual Studio 2017. Gli utenti di destinazione sono agli sviluppatori di Visual Studio che non hanno familiarità a F #.

## <a name="other-useful-resources"></a>Altre risorse utili

Il [sito Web di frammenti di codice F #](http://www.fssnip.net) contiene un set di frammenti di codice viene illustrato come eseguire praticamente qualsiasi elemento in F #, comprese tra principianti ai frammenti avanzati massa.

Il [F # Software Foundation Slack](http://fsharp.org/guides/slack/) è ideale per principianti ed esperti simili, è molto attivi e presenta alcuni dei migliori F # programmatori mondo disponibili per una chat. Si consiglia di unione.

## <a name="the-f-software-foundation"></a>F# Software Foundation

Anche se Microsoft è quello dello sviluppatore primario del linguaggio F # e relativi strumenti di Visual Studio, F # è anche supportato da una base indipendente, di F # Software Foundation (FSSF).

La missione della F# Software Foundation è promuovere, proteggere e migliorare il linguaggio di programmazione F# e supportare e agevolare la crescita di una comunità varia e internazionale di programmatori F#.

Per altre informazioni e per prendere parte a questa iniziativa, vedere [fsharp.org](http://fsharp.org). È disponibile per l'aggiunta e la rete di F # sviluppatori in foundation è un elemento che non si desidera perdere:!
