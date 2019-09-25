---
title: Uso di Gestione pacchetti F# con per Azure
description: Usare Paket o NuGet per gestire F# le dipendenze di Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 4aa32ace91f30d0e43b9c40067f5f0f456cc4069
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214221"
---
# <a name="package-management-for-f-azure-dependencies"></a>Gestione dei pacchetti per le dipendenze F# di Azure

Il recupero di pacchetti per lo sviluppo in Azure è semplice quando si usa una gestione pacchetti. Le due opzioni sono [Paket](https://fsprojects.github.io/Paket/) e [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Uso di Paket

Se si usa il [pacchetto](https://fsprojects.github.io/Paket/) di gestione delle dipendenze, è possibile usare lo `paket.exe` strumento per aggiungere le dipendenze di Azure. Ad esempio:

```console
> paket add nuget WindowsAzure.Storage
```

In alternativa, se si usa [mono](https://www.mono-project.com/) per lo sviluppo .NET multipiattaforma:

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

Questa operazione verrà `WindowsAzure.Storage` aggiunta al set di dipendenze del pacchetto per il progetto nella directory corrente, modificare `paket.dependencies` il file e scaricare il pacchetto. Se in precedenza sono state impostate dipendenze o si sta lavorando a un progetto in cui le dipendenze sono state configurate da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale come segue:

```console
> paket install
```

Oppure, per lo sviluppo mono:

```console
> mono paket.exe install
```

È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente come la seguente:

```console
> paket update
```

Oppure, per lo sviluppo mono:

```console
> mono paket.exe update
```

## <a name="using-nuget"></a>Uso di NuGet

Se si usa [NuGet](https://www.nuget.org/) come gestore delle dipendenze, è possibile usare lo `nuget.exe` strumento per aggiungere le dipendenze di Azure. Ad esempio:

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

Oppure, per lo sviluppo mono:

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Questa operazione verrà `WindowsAzure.Storage` aggiunta al set di dipendenze del pacchetto per il progetto nella directory corrente e scaricherà il pacchetto. Se in precedenza sono state impostate dipendenze o si sta lavorando a un progetto in cui le dipendenze sono state configurate da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale come segue:

```console
> nuget restore
```

Oppure, per lo sviluppo mono:

```console
> mono nuget.exe restore
```

È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente come la seguente:

```console
> nuget update
```

Oppure, per lo sviluppo mono:

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a>Assembly di riferimento

Per utilizzare i pacchetti nello F# script, è necessario fare riferimento agli assembly inclusi nei pacchetti utilizzando una `#r` direttiva. Ad esempio:

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

Come si può notare, è necessario specificare il percorso relativo della DLL e il nome completo della DLL, che potrebbe non corrispondere esattamente al nome del pacchetto. Il percorso includerà una versione del Framework ed eventualmente un numero di versione del pacchetto. Per trovare tutti gli assembly installati, è possibile usare un elemento simile al seguente in una riga di comando di Windows:

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

O in una shell UNIX, simile alla seguente:

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

In questo modo si otterranno i percorsi degli assembly installati. Da qui è possibile selezionare il percorso corretto per la versione del Framework.
