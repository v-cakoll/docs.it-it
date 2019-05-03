---
title: Usare Gestione pacchetti con F# per Azure
description: Usare Paket o Nuget per gestire F# dipendenze di Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756533"
---
# <a name="package-management-for-f-azure-dependencies"></a>Gestione dei pacchetti per le dipendenze F# di Azure

Acquisizione di pacchetti per lo sviluppo di Azure è semplice quando si utilizza una gestione pacchetti. Esistono due opzioni [Paket](https://fsprojects.github.io/Paket/) e [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Usando Paket

Se si usa [Paket](https://fsprojects.github.io/Paket/) il gestore delle dipendenze, è possibile usare il `paket.exe` dello strumento per aggiungere dipendenze di Azure. Ad esempio:

    > paket add nuget WindowsAzure.Storage

Oppure, se si usa [Mono](https://www.mono-project.com/) per sviluppo multipiattaforma con .NET:

    > mono paket.exe add nuget WindowsAzure.Storage

Verrà aggiunto `WindowsAzure.Storage` al set di dipendenze di pacchetto per il progetto nella directory corrente, modificare il `paket.dependencies` file e scaricare il pacchetto. Se si sono state impostate precedentemente le dipendenze, o si lavora con un progetto in cui le dipendenze sono state impostate da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale come segue:

    > paket install

Oppure, per lo sviluppo di Mono:

    > mono paket.exe install

È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente simile al seguente:

    > paket update

Oppure, per lo sviluppo di Mono:

    > mono paket.exe update

## <a name="using-nuget"></a>Uso di Nuget

Se si usa [NuGet](https://www.nuget.org/) il gestore delle dipendenze, è possibile usare il `nuget.exe` dello strumento per aggiungere dipendenze di Azure. Ad esempio:

    > nuget install WindowsAzure.Storage -ExcludeVersion

Oppure, per lo sviluppo di Mono:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

Consente di aggiungere `WindowsAzure.Storage` nel set di dipendenze di pacchetto per il progetto nella directory corrente e scaricare il pacchetto. Se si sono state impostate precedentemente le dipendenze, o si lavora con un progetto in cui le dipendenze sono state impostate da un altro sviluppatore, è possibile risolvere e installare le dipendenze in locale come segue:

    > nuget restore 

Oppure, per lo sviluppo di Mono:

    > mono nuget.exe restore

È possibile aggiornare tutte le dipendenze del pacchetto alla versione più recente simile al seguente:

    > nuget update

Oppure, per lo sviluppo di Mono:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>Assembly di riferimento

Per usare i pacchetti in di F# script, è necessario fare riferimento l'assembly inclusi nei pacchetti usando una `#r` direttiva. Ad esempio:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

Come può notare, è necessario specificare il percorso relativo per la DLL e il nome completo della DLL, che potrebbe non essere esattamente lo stesso come il nome del pacchetto. Il percorso include una versione di framework e possibilmente un numero di versione del pacchetto. Per trovare tutti gli assembly installati, è possibile usare codice simile al seguente in una riga di comando di Windows:

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

In alternativa, in una shell Unix, simile a questo:

    > find packages/WindowsAzure.Storage -name "*.dll"

Questo fornirà i percorsi agli assembly installato. Da qui, è possibile selezionare il percorso corretto per la versione di framework.
