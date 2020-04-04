---
title: Tagliare le applicazioni autonome
description: Scopri come tagliare le app autonome per ridurne le dimensioni. .NET Core raggruppa il runtime con un'app pubblicata in modo autonomo e in genere include più tempo di runtime.
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665635"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Tagliare distribuzioni ed eseguibili autonomi

Quando si pubblica un'applicazione autonoma, il runtime di .NET Core viene fornito insieme all'applicazione. Questo raggruppamento aggiunge una quantità significativa di contenuto all'applicazione in pacchetto.

Quando si tratta di distribuire l'applicazione, le dimensioni sono spesso un fattore importante. Mantenere le dimensioni dell'applicazione del pacchetto il più piccolo possibile è in genere un obiettivo per gli sviluppatori di applicazioni.

A seconda della complessità dell'applicazione, è necessario solo un sottoinsieme del runtime per eseguire l'applicazione. Queste parti inutilizzate del runtime non sono necessarie e possono essere tagliate dall'applicazione in pacchetto.

> [!NOTE]
> Il taglio è una funzionalità sperimentale in .NET Core 3.1 ed è disponibile _solo_ per le applicazioni pubblicate autonome.

## <a name="trim-your-application"></a>Tagliare l'applicazione

L'esempio seguente mostra come tagliare l'applicazione utilizzando il comando [dotnet publish:](../tools/dotnet-publish.md)

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

La funzionalità di taglio funziona esaminando i file binari dell'applicazione per individuare e compilare un grafico degli assembly di runtime necessari. Gli assembly di runtime rimanenti a cui non viene fatto riferimento vengono tagliati.

## <a name="trimming-issues-when-using-reflection"></a>Tagliare i problemi quando si usa la reflection

Esistono scenari in cui la funzionalità di taglio non riuscirà a rilevare i riferimenti. Ad esempio, un'applicazione che utilizza la reflection potrebbe incorrere in questo problema perché la dipendenza dall'assembly sarà nota solo in fase di esecuzione.

Il taglio è un problema solo se l'utilizzo della reflection dipende da un assembly di runtime a cui non viene fatto riferimento direttamente. Tenere presente che il codice dell'applicazione potrebbe non utilizzare direttamente la reflection, ma è possibile che venga utilizzato da un assembly di terze parti a cui si fa riferimento.

Quando il codice fa riferimento a un'API tramite reflection e non si desidera che il linker tagli l'assembly che contiene tale API, è possibile modificare il file di progetto per escludere l'assembly dal processo di taglio. Nell'esempio seguente viene illustrato `System.Security` come impedire che un assembly chiamato venga tagliato:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a>Vedere anche

- [Distribuzione di applicazioni .NET Core](index.md)
