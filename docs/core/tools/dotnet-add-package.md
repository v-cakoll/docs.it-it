---
title: Comando dotnet add package
description: Il comando 'dotnet add package' offre un'opzione utile per aggiungere un riferimento al pacchetto NuGet in un progetto.
ms.date: 06/26/2019
ms.openlocfilehash: 210dcf0efe06672264ebfa297589bdb387591a42
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733323"
---
# <a name="dotnet-add-package"></a>dotnet add package

**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet add package`: aggiunge il riferimento al pacchetto in un file di progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a>Descrizione

Il comando `dotnet add package` offre un'opzione utile per aggiungere riferimenti al pacchetto in un file di progetto. Dopo l'esecuzione del comando, viene eseguito un controllo di compatibilità per verificare che il pacchetto sia compatibile con i framework del progetto. Se il controllo ha esito positivo, al file di progetto viene aggiunto un elemento `<PackageReference>` e viene eseguito [dotnet restore](dotnet-restore.md).

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

Ad esempio, l'aggiunta di `Newtonsoft.Json` a *ToDo.csproj* determina un output simile all'esempio seguente:

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

Il file *ToDo.csproj* contiene ora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) per il pacchetto a cui viene fatto riferimento.

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a>Argomenti

- **`PROJECT`**

  Specifica il file di progetto. Se non specificato, il comando ne cerca uno nella directory corrente.

- **`PACKAGE_NAME`**

  Riferimento al pacchetto da aggiungere.

## <a name="options"></a>Opzioni

- **`-f|--framework <FRAMEWORK>`**

  Aggiunge un riferimento al pacchetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione). Disponibile a partire da .NET Core 2.1 SDK, versione 2.1.400 o successiva.

- **`-n|--no-restore`**

  Aggiunge un riferimento al pacchetto senza eseguire l'anteprima del ripristino e il controllo di compatibilità.

- **`--package-directory <PACKAGE_DIRECTORY>`**

  La directory in cui ripristinare i pacchetti. Il percorso di ripristino del pacchetto predefinito è `%userprofile%\.nuget\packages` in Windows e `~/.nuget/packages` in macOS e Linux. Per altre informazioni, vedere [Gestione delle cartelle dei pacchetti globale, della cache e temporanea in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders).

- **`-s|--source <SOURCE>`**

  L'origine del pacchetto NuGet da usare durante l'operazione di ripristino.

- **`-v|--version <VERSION>`**

  Versione del pacchetto. Vedere [Controllo delle versioni dei pacchetti NuGet](https://docs.microsoft.com/nuget/reference/package-versioning).

## <a name="examples"></a>Esempi

- Aggiungere un pacchetto NuGet `Newtonsoft.Json` in un progetto:

  ```dotnetcli
  dotnet add package Newtonsoft.Json
  ```

- Aggiungere una versione specifica di un pacchetto in un progetto:

  ```dotnetcli
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

- Aggiungere un pacchetto usando un'origine NuGet specifica:

  ```dotnetcli
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a>Vedere anche

- [Gestione delle cartelle dei pacchetti globale, della cache e temporanea in NuGet](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [Controllo delle versioni dei pacchetti NuGet](https://docs.microsoft.com/nuget/reference/package-versioning)
