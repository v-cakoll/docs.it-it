---
title: Creare un pacchetto NuGet con il interfaccia della riga di comando di .NET Core
description: Informazioni su come creare un pacchetto NuGet con il comando 'dotnet pack'.
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 3f8e75a501cfc48e1c416f71e91290cab1a4ffae
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920916"
---
# <a name="how-to-create-a-nuget-package-with-the-net-core-cli"></a>Come creare un pacchetto NuGet con il interfaccia della riga di comando di .NET Core

> [!NOTE]
> Di seguito sono riportati esempi dalla riga di comando che usano Unix. Il comando `dotnet pack` funziona allo stesso modo in Windows, come illustrato di seguito.

Le librerie .NET Standard e .NET Core devono essere distribuite come pacchetti NuGet. È infatti in questo modo che tutte le librerie .NET Standard vengono distribuite e utilizzate. La modalità più semplice per eseguire tale distribuzione è l'uso del comando `dotnet pack`.

Si supponga di aver scritto una nuova libreria da distribuire tramite NuGet. Per eseguire questa operazione, è possibile creare un pacchetto NuGet con strumenti multipiattaforma. Nell'esempio seguente si presuppone una libreria denominata **SuperAwesomeLibrary** che ha come destinazione `netstandard1.0`.

Se si dispone di dipendenze transitive, ovvero un progetto che dipende da un altro pacchetto, assicurarsi di ripristinare i pacchetti per l'intera soluzione con il comando `dotnet restore` prima di creare un pacchetto NuGet. In caso contrario, il comando `dotnet pack` non funzionerà correttamente.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Dopo aver verificato che i pacchetti siano stati ripristinati, è possibile passare alla directory in cui si trova una libreria:

```console
cd src/SuperAwesomeLibrary
```

Quindi è sufficiente eseguire un singolo comando dalla riga di comando:

```dotnetcli
dotnet pack
```

La cartella */bin/debug verranno incluse* sarà ora simile alla seguente:

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Verrà generato un pacchetto di cui è in grado di eseguire il debug. Se si vuole creare un pacchetto NuGet con i file binari della versione, è sufficiente aggiungere l'opzione `--configuration` (o `-c`) e usare `release` come argomento.

```dotnetcli
dotnet pack --configuration release
```

La cartella */bin* includerà ora una cartella della *versione* contenente il pacchetto NuGet con i file binari della versione:

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Sono ora disponibili i file necessari per pubblicare un pacchetto NuGet.

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a>Non confondere `dotnet pack` con `dotnet publish`

È importante notare che il comando `dotnet publish` non viene affatto coinvolto. Il comando `dotnet publish` viene usato per la distribuzione di applicazioni con tutte le relative dipendenze nello stesso bundle, non per la generazione di un pacchetto NuGet per la distribuzione e l'uso mediante NuGet.

## <a name="see-also"></a>Vedere anche

- [Avvio rapido: Creare e pubblicare un pacchetto](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
