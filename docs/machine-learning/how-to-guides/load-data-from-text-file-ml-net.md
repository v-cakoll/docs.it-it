---
title: Caricare dati da un file di testo per l'elaborazione con Machine Learning - ML.NET
description: Informazioni su come caricare dati da un file di testo per usarli nelle attività di creazione, training e assegnazione di punteggio per modelli di Machine Learning con ML.NET
ms.date: 01/29/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 6a8f74cc5324050ca94e60592f083c35afc68377
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479672"
---
# <a name="load-data-from-a-text-file-for-machine-learning-processing---mlnet"></a>Caricare dati da un file di testo per l'elaborazione con Machine Learning - ML.NET

`TextLoader` viene usato per caricare dati da file di testo. È necessario specificare le colonne di dati, i tipi delle colonne e la relativa posizione nel file di testo.

Si noti che è perfettamente accettabile leggere alcune colonne di un file o leggere la stessa colonna più volte.

[File di esempio](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):

```console
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse
```

Per caricare i dati da un file di testo:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
    columns: new TextLoader.Column[]
    {
        // A boolean column depicting the 'target label'.
        new TextLoader.Column("IsOver50k",DataKind.BL,0),
        // Three text columns.
        new TextLoader.Column("WorkClass",DataKind.TX,1),
        new TextLoader.Column("Education",DataKind.TX,2),
        new TextLoader.Column("MaritalStatus",DataKind.TX,3)
    },
    hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(dataPath);
```