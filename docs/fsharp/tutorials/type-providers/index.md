---
title: Provider di tipi
description: "Informazioni su come un provider di tipi F # è un componente che fornisce i tipi, proprietà e metodi per l'uso nei programmi."
ms.date: 04/02/2018
ms.openlocfilehash: 5fa9de229caa2ec3ba4a248ca5cd1c8aa5adb230
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276583"
---
# <a name="type-providers"></a>Provider di tipi

Un provider di tipi F# è un componente che fornisce tipi, proprietà e metodi da utilizzare in un programma. Provider di tipi generano i cosiddetti **forniti tipi**, che vengono generati dal compilatore F # e si basano su un'origine dati esterna.

Ad esempio, un Provider di tipi F # per SQL può generare tipi che rappresentano le tabelle e colonne in un database relazionale. In effetti, questo è ciò che il [SQLProvider](https://fsprojects.github.io/SQLProvider/) provider di tipo.

Forniti che tipi dipendono dai parametri di input per un Provider di tipi. Input di questo tipo può essere un'origine dati di esempio (ad esempio un file di schema JSON), un URL che punta direttamente a un servizio esterno o a una stringa di connessione a un'origine dati. Un Provider di tipi possono anche garantire che i gruppi di tipi siano espandibili solamente su richiesta. vale a dire, vengono espansi se i tipi vengono effettivamente fatto riferimento dal programma. Questo consente di utilizzare l'integrazione diretta su richiesta di spazi di informazioni su larga scala fortemente tipizzati, come i mercati di dati online.

## <a name="generative-and-erased-type-providers"></a>Provider di tipi propria e cancellati

Provider di tipi sono disponibili due tipi: propria e cancellati.

Provider di tipi propria producono i tipi che possono essere scritti come tipi .NET nell'assembly in cui essi vengono generati. In questo modo possono essere usati dal codice in altri assembly. Ciò significa che la rappresentazione in forma tipizzata dell'origine dati deve essere in genere che è possibile rappresentare con i tipi .NET.

Provider di tipi cancellazione produrre tipi che possono essere utilizzati solo nell'assembly o nel progetto da che vengono generati. I tipi sono temporanei; vale a dire, essi non vengono scritti in un assembly e non può essere utilizzati dal codice in altri assembly. Possono contenere *ritardato* membri, consentendo ai tipi di uso fornito da uno spazio di informazioni potenzialmente infinito. Sono utili per l'uso di un piccolo subset di un'origine dei dati di grandi dimensioni e interconnesse.

## <a name="commonly-used-type-providers"></a>Comunemente usati provider di tipi

Le seguenti librerie diffuso contengono i provider di tipi per usi diversi:

- [FSharp](https://fsharp.github.io/FSharp.Data/) include il provider di tipi per HTML, XML, CSV e JSON di formati e le risorse di documenti.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) fornisce accesso fortemente tipizzato al database di relazione tramite mapping degli oggetti e LINQ F # le query su tali origini dati.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) dispone di un set di provider di tipi per la fase di compilazione selezionata incorporamento di T-SQL in F #.
- [Provider di tipi di archiviazione Azure](https://fsprojects.github.io/AzureStorageTypeProvider/) fornisce tipi per i BLOB di Azure, tabelle e code, consentendo di accedere a queste risorse senza la necessità di specificare i nomi delle risorse sotto forma di stringhe nell'intero programma.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) contiene il **GraphQLProvider**, che fornisce i tipi basati su un server GraphQL specificato dall'URL.

Se necessario, è possibile [creare il proprio provider di tipi personalizzati](creating-a-type-provider.md), o fare riferimento a provider di tipi che sono stati creati da altri utenti. Ad esempio, si supponga che l'organizzazione abbia un servizio dati che fornisce un numero elevato e crescente di set di dati denominati, ciascuno con il proprio schema dati stabile. È possibile scegliere di creare un provider di tipi che legge gli schemi ed elenca gli ultimi set di dati disponibili per il programmatore, in una modalità fortemente tipizzata.

## <a name="see-also"></a>Vedere anche

- [Esercitazione: Creare un Provider di tipi](creating-a-type-provider.md)
- [Riferimenti per il linguaggio F#](../../language-reference/index.md)
- [Visual F#](../../index.md)
