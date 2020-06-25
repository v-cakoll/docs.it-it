---
title: Installare e gestire modelli SDK-.NET Core
description: Informazioni su come installare i modelli .NET Core in Windows, Linux e macOS.
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324497"
---
# <a name="manage-net-project-and-item-templates"></a>Gestire modelli di progetti e di elementi .NET

.NET Core fornisce un sistema di modelli che consente agli utenti di installare o disinstallare modelli da NuGet, da un file di pacchetto NuGet o da una directory file system. Questo articolo descrive come gestire i modelli .NET Core tramite l'interfaccia della riga di comando .NET Core SDK.

Per ulteriori informazioni sulla creazione di modelli, vedere [esercitazione: creare modelli](../tutorials/cli-templates-create-item-template.md).

## <a name="install-template"></a>Installa modello

I modelli vengono installati tramite il [dotnet new](../tools/dotnet-new.md) comando SDK con il `-i` parametro. È possibile specificare l'identificatore del pacchetto NuGet di un modello o una cartella che contiene i file modello.

### <a name="nuget-hosted-package"></a>Pacchetto NuGet ospitato

I modelli dell'interfaccia della riga di comando .NET vengono caricati in [NuGet](https://www.nuget.org/) per la distribuzione estesa. I modelli possono anche essere installati da un feed privato. Anziché caricare un modello in un feed NuGet, i file di modello *nupkg* possono essere distribuiti e installati manualmente, come descritto nella sezione [pacchetto NuGet locale](#local-nuget-package) .

Per ulteriori informazioni sulla configurazione dei feed NuGet, vedere [dotnet nuget add source](../tools/dotnet-nuget-add-source.md) .

Per installare un pacchetto di modelli dal feed NuGet predefinito, usare il `dotnet new -i {package-id}` comando:

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

Per installare un pacchetto di modelli dal feed NuGet predefinito con una versione specifica, usare il `dotnet new -i {package-id}::{version}` comando:

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a>Pacchetto NuGet locale

Quando viene creato un pacchetto di modelli, viene generato un file *nupkg* . Se si dispone di un file *nupkg* che contiene modelli, è possibile installarlo con il `dotnet new -i {path-to-package}` comando:

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a>Cartella

In alternativa all'installazione di un modello da un file *nupkg* , è anche possibile installare modelli da una cartella direttamente con il `dotnet new -i {folder-path}` comando. La cartella specificata viene considerata come identificatore del pacchetto di modelli per tutti i modelli trovati. Viene installato qualsiasi modello trovato nella gerarchia della cartella specificata.

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

Il `{folder-path}` parametro specificato nel comando diventa l'identificatore del pacchetto di modelli per tutti i modelli trovati. Come specificato nella sezione [modelli elenco](#list-templates) , è possibile ottenere un elenco dei modelli installati con il `dotnet new -u` comando. In questo esempio, l'identificatore del pacchetto di modelli viene visualizzato come cartella usata per l'installazione:

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a>Disinstalla modello

I modelli vengono disinstallati tramite il [dotnet new](../tools/dotnet-new.md) comando SDK con il `-u` parametro. È possibile specificare l'identificatore del pacchetto NuGet di un modello o una cartella che contiene i file modello.

### <a name="nuget-package"></a>Pacchetto NuGet

Dopo l'installazione di un pacchetto di modelli NuGet, da un feed NuGet o da un file *nupkg* , è possibile disinstallarlo facendo riferimento all'identificatore del pacchetto NuGet.

Per disinstallare un pacchetto di modelli, usare il `dotnet new -u {package-id}` comando:

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a>Cartella

Quando si installano i modelli tramite un [percorso di cartella](#folder), il percorso della cartella diventa l'identificatore del pacchetto di modelli.

Per disinstallare un pacchetto di modelli, usare il `dotnet new -u {package-folder-path}` comando:

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a>Elenca modelli

Utilizzando il comando di disinstallazione standard senza un identificatore del pacchetto, è possibile visualizzare un elenco dei modelli installati insieme al comando che disinstalla ogni modello.

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a>Installare modelli da altri SDK

Se ogni versione dell'SDK è stata installata in modo sequenziale, ad esempio se è stato installato SDK 2,0, SDK 2,1 e così via, saranno installati tutti i modelli di SDK. Tuttavia, se si inizia con una versione più recente dell'SDK, ad esempio 3,1, vengono inclusi solo i modelli per le [versioni LTS (supporto a lungo termine)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che al momento della versione SDK 3,1 sono SDK 2,1 e SDK 3,1. I modelli per qualsiasi altra versione non sono inclusi.

I modelli .NET Core sono disponibili in NuGet ed è possibile installarli come qualsiasi altro modello. Per altre informazioni, vedere [Install NuGet Hosted Package](#nuget-hosted-package).

| SDK              | Identificatore del pacchetto NuGet                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| .NET Core 2.1    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| .NET Core 2.2    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| .NET Core 3.0    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| .NET Core 3.1    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| ASP.NET Core 2.1 | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| ASP.NET Core 2,2 | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| ASP.NET Core 3,0 | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| ASP.NET Core 3,1 | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

Ad esempio, il .NET Core SDK include modelli per un'app console destinata a .NET Core 2,1 e .NET Core 3,1. Se si vuole specificare come destinazione .NET Core 3,0, è necessario installare i modelli 3,0.

01. Provare a creare un'app destinata a .NET Core 3,0.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    Se viene visualizzato un messaggio di errore, è necessario installare i modelli.

    > Non è stato trovato alcun modello installato che corrisponda all'input, che esegue la ricerca online...

01. Installare i modelli di progetto .NET Core 3,0.

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. Provare a creare l'app una seconda volta.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    Verrà visualizzato un messaggio che indica che il progetto è stato creato.

    > Creazione del modello "applicazione console" completata.
    >
    > Elaborazione delle azioni di post-creazione... Esecuzione di ' dotnet restore ' in path-to-Project-file. csproj in corso... Determinazione progetti da ripristinare... Il ripristino è stato completato in 1,05 secondi per path-to-Project-file. csproj.
    >
    > Ripristino completato.

## <a name="see-also"></a>Vedi anche

- [Esercitazione: creare un modello di elemento](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
