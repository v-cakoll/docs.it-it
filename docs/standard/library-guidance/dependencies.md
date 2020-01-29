---
title: Dipendenze e librerie .NET
description: Procedure consigliate per la gestione delle dipendenze NuGet nelle librerie .NET.
ms.date: 10/02/2018
ms.openlocfilehash: 6a260b54c45a0cd231059ab3bc6f2707ef7fb20e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731486"
---
# <a name="dependencies"></a>Dipendenze

Il modo principale per aggiungere dipendenze a una libreria .NET consiste nel fare riferimento ai pacchetti NuGet. I riferimenti ai pacchetti NuGet consentono di riutilizzare rapidamente e di sfruttare le funzionalità già scritte, ma possono causare problemi per gli sviluppatori .NET. La corretta gestione delle dipendenze è importante per evitare che le modifiche apportate in altre librerie .NET impediscano il funzionamento della libreria .NET in uso e viceversa.

## <a name="diamond-dependencies"></a>Dipendenze a rombo

In un progetto .NET è comune la presenza di più versioni di un pacchetto nel relativo albero delle dipendenze. Ad esempio, un'app dipende da due pacchetti NuGet, ognuno dei quali dipende da versioni diverse dello stesso pacchetto. Nel grafo delle dipendenze dell'app è ora presente una dipendenza a rombo.

![Dipendenza Diamond](./media/dependencies/diamond-dependency.png "Dipendenza Diamond")

In fase di compilazione NuGet analizza tutti i pacchetti da cui un progetto dipende, incluse le dipendenze delle dipendenze. Quando vengono rilevate più versioni di un pacchetto, vengono valutate le regole per scegliere un pacchetto. È necessario unificare i pacchetti perché l'esecuzione affiancata di versioni diverse di un assembly nella stessa applicazione è problematica in .NET.

La maggior parte delle dipendenze a rombo può essere risolta facilmente, tuttavia in alcune circostanze è possibile che si verifichino problemi:

1. I **riferimenti ai pacchetti NuGet in conflitto** impediscono la risoluzione di una versione durante il ripristino dei pacchetti.
2. Le **modifiche tra versioni che causano un'interruzione** provocano bug ed eccezioni in fase di esecuzione.
3. L'**assembly del pacchetto ha un nome sicuro**, la versione dell'assembly è stata modificata e l'app è in esecuzione in .NET Framework. Sono richiesti reindirizzamenti di binding dell'assembly.

Non è possibile sapere quali pacchetti verranno usati insieme ai propri. Un buon metodo per ridurre le probabilità che una dipendenza a rombo provochi il malfunzionamento della libreria consiste nel ridurre al minimo il numero di pacchetti da cui la libreria dipende.

✔️ rivedere la libreria .NET per le dipendenze non necessarie.

## <a name="nuget-dependency-version-ranges"></a>Intervalli di versione delle dipendenze NuGet

Un riferimento a un pacchetto specifica l'intervallo di pacchetti validi consentiti. In genere, la versione di riferimento del pacchetto nel file di progetto è la versione minima e non è previsto alcun limite massimo.

```xml
<!-- Accepts any version 1.0 and above. -->
<PackageReference Include="ExamplePackage" Version="1.0" />
```

Le regole usate da NuGet per la risoluzione delle dipendenze sono [complesse](/nuget/consume-packages/dependency-resolution), ma NuGet cerca sempre la versione più bassa applicabile. NuGet privilegia la versione più bassa applicabile rispetto all'uso della versione più alta disponibile perché la più bassa presenta meno problemi di compatibilità.

A causa della regola di ricerca della versione più bassa applicabile da parte di NuGet, non è necessario inserire una versione superiore o un intervallo esatto nei riferimenti ai pacchetti per evitare di ottenere la versione più recente. NuGet cerca già di trovare la versione più bassa e più compatibile.

```xml
<!-- Accepts 1.0 up to 1.x, but not 2.0 and higher. -->
<PackageReference Include="ExamplePackage" Version="[1.0,2.0)" />

<!-- Accepts exactly 1.0. -->
<PackageReference Include="ExamplePackage" Version="[1.0]" />
```

I limiti superiori per la versione provocano un errore di NuGet in caso di conflitto. Ad esempio, una libreria accetta esattamente la versione 1.0, mentre un'altra libreria richiede la versione 2.0 o successiva. Sebbene nella versione 2.0 potrebbero essere state introdotte modifiche che causano un'interruzione, una dipendenza di versione rigida o con un limite superiore garantisce la generazione di un errore.

![Conflitto tra dipendenze Diamond](./media/dependencies/diamond-dependency-conflict.png "Conflitto tra dipendenze Diamond")

❌ non hanno riferimenti ai pacchetti NuGet senza versione minima.

❌ evitare i riferimenti ai pacchetti NuGet che richiedono una versione esatta.

❌ evitare i riferimenti ai pacchetti NuGet con un limite superiore della versione.

## <a name="nuget-shared-source-packages"></a>Pacchetti di codice sorgente condiviso NuGet

Un modo per ridurre le dipendenze esterne dei pacchetti NuGet consiste nel fare riferimento a pacchetti di codice sorgente condiviso. Un pacchetto di codice sorgente condiviso contiene [file di codice sorgente](/nuget/reference/nuspec#including-content-files) che vengono inclusi in un progetto quando vi viene fatto riferimento. Perché vengono inclusi solo i file di codice sorgente compilati con il resto del progetto, non c'è alcuna dipendenza esterna e di conseguenza non c'è possibilità di conflitto.

I pacchetti di codice sorgente condiviso sono ideali per includere funzionalità di piccola entità. Ad esempio, un pacchetto di codice sorgente condiviso di metodi helper per l'esecuzione di chiamate HTTP.

![Pacchetto di origine condivisa](./media/dependencies/shared-source-package.png "Pacchetto di origine condivisa")

```xml
<PackageReference Include="Microsoft.Extensions.Buffers.Testing.Sources" PrivateAssets="All" Version="1.0" />
```

![Progetto di origine condivisa](./media/dependencies/shared-source-project.png "Progetto di origine condivisa")

I pacchetti di codice sorgente condiviso presentano alcune limitazioni. È possibile farvi riferimento solo tramite `PackageReference`, quindi i progetti `packages.config` precedenti sono esclusi. I pacchetti di codice sorgente condiviso, inoltre, possono essere usati solo da progetti con lo stesso tipo di linguaggio. A causa di queste limitazioni, è preferibile usare i pacchetti di codice sorgente condiviso per condividere funzionalità in un progetto open source.

✔️ considerare la possibilità di fare riferimento a pacchetti di origine condivisi per piccoli componenti interni di funzionalità.

✔️ considerare la possibilità di creare un pacchetto di origine condiviso per il pacchetto se fornisce funzionalità interne di piccole dimensioni.

✔️ FANNO riferimento a pacchetti di origine condivisi con `PrivateAssets="All"`.

> Questa impostazione indica a NuGet che il pacchetto deve essere usato solo in fase di sviluppo e non deve essere esposto come dipendenza pubblica.

❌ non hanno tipi di pacchetti di origine condivisi nell'API pubblica.

> I tipi di codice sorgente condiviso vengono compilati nell'assembly di riferimento e non possono essere scambiati tra assembly diversi. Ad esempio, un tipo `IRepository` di codice sorgente condiviso in un progetto è un tipo diverso dallo stesso oggetto `IRepository` di codice sorgente condiviso in un altro progetto. I tipi nei pacchetti di codice sorgente condiviso devono avere visibilità `internal`.

❌ non pubblicare pacchetti di origine condivisi in NuGet.org.

> I pacchetti di codice sorgente condiviso contengono codice sorgente e possono essere usati solo da progetti con lo stesso tipo di linguaggio. Ad esempio, un pacchetto di codice sorgente condiviso C# non può essere usato da un'applicazione F#.
>
> Pubblicare i pacchetti di codice sorgente condiviso in un [feed locale o MyGet](./publish-nuget-package.md) per usarli internamente all'interno del progetto.

>[!div class="step-by-step"]
>[Precedente](nuget.md)
>[Successivo](sourcelink.md)
