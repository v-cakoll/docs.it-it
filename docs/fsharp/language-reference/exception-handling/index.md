---
title: Gestione delle eccezioni (F#)
description: 'Nozioni di base di gestione delle eccezioni in F # e collegamenti a espressioni e funzioni di gestione delle eccezioni.'
ms.date: 05/16/2016
ms.openlocfilehash: fc89feb0d21bc823cb105e435413f8309cd6174c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="exception-handling"></a>Gestione delle eccezioni

Questa sezione contiene informazioni sul supporto di gestione delle eccezioni nel linguaggio F#.


## <a name="exception-handling-basics"></a>Nozioni fondamentali sulla gestione delle eccezioni
La gestione delle eccezioni è il modo standard per la gestione delle condizioni degli errori in .NET Framework. Qualsiasi linguaggio .NET deve quindi supportare questo meccanismo, incluso F#. Un'*eccezione* è un oggetto che incapsula informazioni su un errore. Quando si verificano errori, vengono generate eccezioni e viene interrotta l'esecuzione normale. Il runtime cerca invece un gestore appropriato per l'eccezione. La ricerca inizia nella funzione corrente e procede verso l'alto attraverso i livelli di chiamanti fino a quando non viene trovato un gestore corrispondente. Quindi viene eseguito il gestore.

Mentre lo stack viene rimosso, il runtime esegue anche tutti i codice nei blocchi `finally` per garantire che gli oggetti vengano puliti correttamente durante il processo di rimozione.


## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----|-----------|
|[Tipi di eccezione](exception-types.md)|Descrive come dichiarare un tipo di eccezione.|
|[Eccezioni: espressione `try...with`](the-try-with-expression.md)|Descrive il costrutto di linguaggio che supporta la gestione delle eccezioni.|
|[Eccezioni: espressione `try...finally`](the-try-finally-expression.md)|Descrive il costrutto di linguaggio che consente di eseguire il codice di pulizia mentre lo stack viene rimosso se viene generata un'eccezione.|
|[Eccezioni: funzione `raise`](the-raise-Function.md)|Descrive come generare un oggetto eccezione.|
|[Eccezioni: funzione `failwith`](the-failwith-function.md)|Descrive come generare un'eccezione F# generale.|
|[Eccezioni: funzione `invalidArg`](the-invalidArg-function.md)|Descrive come generare un'eccezione di argomento non valido.|
