---
title: Provider di tipi
description: 'Informazioni su come un provider di tipi F # è un componente che fornisce tipi, proprietà e metodi da utilizzare nei programmi.'
ms.date: 04/02/2018
ms.openlocfilehash: eae64d2e318ee93f0b8d5b91f0c6da6c91743527
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202102"
---
# <a name="type-providers"></a>Provider di tipi

Un provider di tipi F# è un componente che fornisce tipi, proprietà e metodi da utilizzare in un programma. I provider di tipi generano gli elementi noti come **tipi forniti**, che vengono generati dal compilatore F # e sono basati su un'origine dati esterna.

Un provider di tipi F # per SQL, ad esempio, può generare tipi che rappresentano tabelle e colonne in un database relazionale. In realtà, si tratta del provider [di tipi SqlProvider.](https://fsprojects.github.io/SQLProvider/)

I tipi forniti dipendono dai parametri di input di un provider di tipi. Tale input può essere un'origine dati di esempio, ad esempio un file di schema JSON, un URL che punta direttamente a un servizio esterno o una stringa di connessione a un'origine dati. Un provider di tipi può inoltre garantire che i gruppi di tipi vengano espansi solo su richiesta. ovvero vengono espansi se il programma fa effettivamente riferimento ai tipi. Questo consente di utilizzare l'integrazione diretta su richiesta di spazi di informazioni su larga scala fortemente tipizzati, come i mercati di dati online.

## <a name="generative-and-erased-type-providers"></a>Provider di tipi generativi e cancellati

I provider di tipi sono disponibili in due forme: generative e cancellate.

I provider di tipi generativi producono tipi che possono essere scritti come tipi .NET nell'assembly in cui vengono prodotti. Ciò consente di utilizzare il codice in altri assembly. Ciò significa che la rappresentazione tipizzata dell'origine dati deve essere in genere quella che è possibile rappresentare con i tipi .NET.

La cancellazione dei provider di tipi produce tipi che possono essere utilizzati solo nell'assembly o nel progetto da cui vengono generati. I tipi sono effimeri; ovvero non vengono scritte in un assembly e non possono essere utilizzate dal codice in altri assembly. Possono contenere membri *ritardati* , consentendo di usare i tipi forniti da uno spazio informatico potenzialmente infinito. Sono utili per usare un piccolo subset di un'origine dati di grandi dimensioni e interconnesse.

## <a name="commonly-used-type-providers"></a>Provider di tipi comunemente utilizzati

Le seguenti librerie di uso frequente contengono provider di tipi per usi diversi:

- [FSharp. Data](https://fsharp.github.io/FSharp.Data/) include provider di tipi per le risorse e i formati di documento JSON, XML, CSV e HTML.
- [Sqlfornitor](https://fsprojects.github.io/SQLProvider/) fornisce accesso fortemente tipizzato ai database di relazione tramite il mapping degli oggetti e le query LINQ F # su tali origini dati.
- [FSharp. Data. SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) include un set di provider di tipi per l'incorporamento di T-SQL selezionato in fase di compilazione in F #.
- Il [provider del tipo di archiviazione di Azure](https://fsprojects.github.io/AzureStorageTypeProvider/) fornisce i tipi per BLOB, tabelle e code di Azure, consentendo di accedere a queste risorse senza dover specificare i nomi delle risorse come stringhe nel programma.
- [FSharp. Data. GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) contiene **GraphQLProvider**, che fornisce tipi basati su un server GraphQL specificato dall'URL.

Se necessario, è possibile [creare provider di tipi personalizzati](creating-a-type-provider.md)o provider di tipi di riferimento creati da altri. Ad esempio, si supponga che l'organizzazione abbia un servizio dati che fornisce un numero elevato e crescente di set di dati denominati, ciascuno con il proprio schema dati stabile. È possibile scegliere di creare un provider di tipi che legge gli schemi ed elenca gli ultimi set di dati disponibili per il programmatore, in una modalità fortemente tipizzata.

## <a name="see-also"></a>Vedere anche

- [Esercitazione: creare un provider di tipi](creating-a-type-provider.md)
- [Riferimenti per il linguaggio F #](../../language-reference/index.md)
