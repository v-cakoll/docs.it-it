---
title: Creazione di un pacchetto NuGet con strumenti multipiattaforma
description: Informazioni su come creare un pacchetto NuGet con il comando 'dotnet pack'.
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 0be8d302568bc08d2c3dacfdf5738eff4b97d4b2
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2018
ms.locfileid: "48848101"
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a>Come creare un pacchetto NuGet con strumenti multipiattaforma

> [!NOTE]
> Di seguito sono riportati esempi dalla riga di comando che usano Unix.  Il comando `dotnet pack` funziona allo stesso modo in Windows, come illustrato di seguito.

Per .NET Core 1.0, le librerie devono essere distribuite come pacchetti NuGet.  È infatti in questo modo che tutte le librerie .NET Standard vengono distribuite e utilizzate.  La modalità più semplice per eseguire tale distribuzione è l'uso del comando `dotnet pack`.

Si supponga di aver scritto una nuova libreria da distribuire tramite NuGet.  A questo scopo, è possibile creare un pacchetto NuGet con strumenti multipiattaforma.  L'esempio seguente presuppone l'esistenza di una libreria denominata **SuperAwesomeLibrary** che punta a `netstandard1.0`.

In caso di dipendenze transitive, ovvero un progetto che dipende da un altro pacchetto, è necessario assicurarsi di ripristinare i pacchetti per l'intera soluzione con il comando `dotnet restore` prima di creare un pacchetto NuGet.  In caso contrario, il comando `dotnet pack` non funzionerà correttamente.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


Dopo aver verificato che i pacchetti siano stati ripristinati, è possibile passare alla directory in cui si trova una libreria:

`$ cd src/SuperAwesomeLibrary`

Quindi è sufficiente eseguire un singolo comando dalla riga di comando:
    
`$ dotnet pack`

La cartella `/bin/Debug` avrà un aspetto simile al seguente:

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Si noti che in questo modo verrà generato un pacchetto di cui può essere eseguito il debug.  Se si vuole creare un pacchetto NuGet con i file binari della versione, è sufficiente aggiungere l'opzione `-c`/`--configuration` e usare `release` come argomento.

`$ dotnet pack --configuration release`

La cartella `/bin` avrà una cartella `release` contenente il pacchetto NuGet con i file binari della versione:

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Sono ora disponibili i file necessari per pubblicare un pacchetto NuGet.

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a>Non confondere `dotnet pack` con `dotnet publish`

È importante notare che il comando `dotnet publish` non viene affatto coinvolto.  Il comando `dotnet publish` viene usato per la distribuzione di applicazioni con tutte le relative dipendenze nello stesso bundle, non per la generazione di un pacchetto NuGet per la distribuzione e l'uso mediante NuGet.
