---
title: Caricare dati da un file di testo per l'elaborazione con Machine Learning - ML.NET
description: Informazioni su come caricare dati da un file di testo per usarli nelle attività di creazione, training e assegnazione di punteggio per modelli di Machine Learning con ML.NET
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 7b1e8d3fb6047059c14ec3db8450364a84497219
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156559"
---
# <a name="load-data-from-a-text-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="98876-103">Caricare dati da un file di testo per l'elaborazione con Machine Learning - ML.NET</span><span class="sxs-lookup"><span data-stu-id="98876-103">Load data from a text file for machine learning processing - ML.NET</span></span>

<span data-ttu-id="98876-104">`TextLoader` viene usato per caricare dati da file di testo.</span><span class="sxs-lookup"><span data-stu-id="98876-104">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="98876-105">È necessario specificare le colonne di dati, i tipi delle colonne e la relativa posizione nel file di testo.</span><span class="sxs-lookup"><span data-stu-id="98876-105">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="98876-106">Si noti che è perfettamente accettabile leggere alcune colonne di un file o leggere la stessa colonna più volte.</span><span class="sxs-lookup"><span data-stu-id="98876-106">Note that it's perfectly acceptable to read some columns of a file, or read the same column multiple times.</span></span>

<span data-ttu-id="98876-107">[File di esempio](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="98876-107">[Example file](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse
```

<span data-ttu-id="98876-108">Per caricare i dati da un file di testo:</span><span class="sxs-lookup"><span data-stu-id="98876-108">To load the data from a text file:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();
TextLoader textLoader;

// Create the reader: define the data columns and where to find them in the text file.
textLoader = mlContext.Data.TextReader(new TextLoader.Arguments()
{
    Separator = ",",
    HasHeader = true,
    Column = new[]
                {
                    new TextLoader.Column("VendorId", DataKind.Text, 0),
                    new TextLoader.Column("RateCode", DataKind.Text, 1),
                    new TextLoader.Column("PassengerCount", DataKind.R4, 2),
                    new TextLoader.Column("TripTime", DataKind.R4, 3),
                    new TextLoader.Column("TripDistance", DataKind.R4, 4),
                    new TextLoader.Column("PaymentType", DataKind.Text, 5),
                    new TextLoader.Column("FareAmount", DataKind.R4, 6)
                }
}
);

// Now read the file (remember though, readers are lazy, so the reading will happen when the data is accessed).
var data = textLoader.Read(dataPath);
```