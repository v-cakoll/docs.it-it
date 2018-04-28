---
title: Provider di tipi
description: 'Informazioni su come un provider di tipi F # è un componente che fornisce tipi, proprietà e metodi da utilizzare nei programmi.'
author: cartermp
ms.author: phcart
ms.date: 04/02/2018
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 5b7bae6f960b9cfa91188e8eb80be949cda12b65
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="type-providers"></a>Provider di tipi

Un provider di tipi F# è un componente che fornisce tipi, proprietà e metodi da utilizzare in un programma. Provider di tipi generano i cosiddetti **forniti tipi**, che vengono generati dal compilatore F #, basati su un'origine dati esterna.

Ad esempio, un Provider di tipi F # per SQL può generare tipi che rappresentano le tabelle e colonne in un database relazionale. In realtà, questo è ciò che il [SQLProvider](https://fsprojects.github.io/SQLProvider/) tipo Provider non.

Forniti che tipi dipendono dai parametri di input per un Provider di tipi. Input di questo tipo può essere un'origine dati di esempio (ad esempio un file di schema JSON), un URL che punta direttamente a un servizio esterno o una stringa di connessione a un'origine dati. Un Provider di tipi può inoltre garantire che i gruppi di tipi siano espandibili solamente su richiesta; ovvero, vengono espansi se i tipi vengono effettivamente fatto riferimento dal programma. Questo consente di utilizzare l'integrazione diretta su richiesta di spazi di informazioni su larga scala fortemente tipizzati, come i mercati di dati online.

## <a name="generative-and-erased-type-providers"></a>Provider di tipi vedere Generative e cancellate

Provider di tipi sono disponibili in due forme: vedere Generative e cancellate.

Vedere Generative provider di tipi di generare tipi che possono essere scritti come tipi .NET nell'assembly in cui vengono generati. In questo modo possono essere utilizzati dal codice in altri assembly. Ciò significa che la rappresentazione dell'origine dati tipizzata in genere deve essere uno che è possibile rappresentare con i tipi .NET.

Cancellazione provider di tipi di generare tipi che possono essere utilizzati solo nell'assembly o nel progetto da che vengono generati. I tipi sono effimero; vale a dire, essi non vengono scritti in un assembly e non può essere utilizzati dal codice in altri assembly. Possono contenere *ritardato* membri, consentendo ai tipi utilizza fornita da uno spazio di informazioni potenzialmente infinito. Sono utili per l'utilizzo di un piccolo subset di un'origine dati di grandi dimensioni e interconnessi.

## <a name="commonly-used-type-providers"></a>Comunemente utilizzati i provider di tipi

Le seguenti librerie ampiamente diffuso contengono i provider di tipi per usi diversi:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) include i provider di tipi per JSON, XML, CSV e HTML documento formati e le risorse.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) fornisce accesso fortemente tipizzato per i database relazione di mapping degli oggetti e LINQ F # query rispetto a tali origini dati.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) dispone di un set di provider di tipi per la fase di compilazione selezionata durante l'incorporamento di T-SQL in F #.
- [Provider di tipi di archiviazione Azure](https://fsprojects.github.io/AzureStorageTypeProvider/) fornisce tipi per i BLOB di Azure, tabelle e code, consentendo di accedere a tali risorse senza la necessità di specificare i nomi delle risorse come stringhe nell'intero programma.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) contiene il **GraphQLProvider**, che fornisce i tipi basati su un server GraphQL specificato dall'URL.

Se necessario, è possibile [creare i propri provider di tipi personalizzato](creating-a-type-provider.md), o fare riferimento a provider di tipi che sono stati creati da altri utenti. Ad esempio, si supponga che l'organizzazione abbia un servizio dati che fornisce un numero elevato e crescente di set di dati denominati, ciascuno con il proprio schema dati stabile. È possibile scegliere di creare un provider di tipi che legge gli schemi ed elenca gli ultimi set di dati disponibili per il programmatore, in una modalità fortemente tipizzata.

## <a name="see-also"></a>Vedere anche
[Esercitazione: Creare un Provider di tipi](creating-a-type-provider.md)

[Riferimenti per il linguaggio F#](../../language-reference/index.md)

[Visual F#](../../index.md)
