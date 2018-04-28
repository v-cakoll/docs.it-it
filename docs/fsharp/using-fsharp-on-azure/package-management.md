---
title: 'Utilizzo di gestione dei pacchetti con F # per Azure'
description: 'Utilizzare Paket o Nuget per gestire le dipendenze di Azure di F #'
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: da6938c6ee29292571f4269c68a9148c13738422
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="package-management-for-f-azure-dependencies"></a>Gestione dei pacchetti per le dipendenze F# di Azure

Acquisizione di pacchetti per lo sviluppo di Azure è semplice quando si utilizza una gestione pacchetti. Esistono due opzioni [Paket](https://fsprojects.github.io/Paket/) e [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Utilizzando Paket

Se si utilizza [Paket](https://fsprojects.github.io/Paket/) come la gestione delle dipendenze, è possibile utilizzare il `paket.exe` strumento per aggiungere dipendenze di Azure. Ad esempio:

    > paket add nuget WindowsAzure.Storage

Oppure, se si utilizza [Mono](https://www.mono-project.com/) per lo sviluppo multipiattaforma con .NET:

    > mono paket.exe add nuget WindowsAzure.Storage

Verrà aggiunta `WindowsAzure.Storage` al set di dipendenze di pacchetto per il progetto nella directory corrente, modificare il `paket.dependencies` file e scaricare il pacchetto. Se si hanno impostato le dipendenze in precedenza o si lavora con un progetto in cui sono state impostate dipendenze da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale simile al seguente:

    > paket install

Oppure, per lo sviluppo Mono:

    > mono paket.exe install

È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente simile al seguente:

    > paket update

Oppure, per lo sviluppo Mono:

    > mono paket.exe update

## <a name="using-nuget"></a>Uso di Nuget

Se si utilizza [NuGet](https://www.nuget.org/) come la gestione delle dipendenze, è possibile utilizzare il `nuget.exe` strumento per aggiungere dipendenze di Azure. Ad esempio:

    > nuget install WindowsAzure.Storage -ExcludeVersion

Oppure, per lo sviluppo Mono:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

Verrà aggiunta `WindowsAzure.Storage` al set di dipendenze di pacchetto per il progetto nella directory corrente e il download del pacchetto. Se si hanno impostato le dipendenze in precedenza o si lavora con un progetto in cui sono state impostate dipendenze da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale simile al seguente:

    > nuget restore 

Oppure, per lo sviluppo Mono:

    > mono nuget.exe restore

È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente simile al seguente:

    > nuget update

Oppure, per lo sviluppo Mono:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>Assembly di riferimento

Per utilizzare i pacchetti nello script F #, è necessario fare riferimento gli assembly inclusi nei pacchetti utilizzando un `#r` direttiva. Ad esempio:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

Come si può notare, è necessario specificare il percorso relativo per la DLL e il nome completo della DLL, che potrebbe non essere esattamente lo stesso come il nome del pacchetto. Il percorso include una versione di framework ed eventualmente un numero di versione del pacchetto. Per trovare tutti gli assembly installati, è possibile utilizzare codice simile al seguente su una riga di comando di Windows:

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

O in una shell Unix, simile a questo:

    > find packages/WindowsAzure.Storage -name "*.dll"

Questa query fornirà i percorsi per gli assembly installati. Da qui, è possibile selezionare il percorso corretto per la versione di framework.
