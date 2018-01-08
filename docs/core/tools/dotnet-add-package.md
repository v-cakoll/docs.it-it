---
title: Comando dotnet add package - Interfaccia della riga di comando di .NET Core
description: Il comando 'dotnet add package' offre un'opzione utile per aggiungere un riferimento al pacchetto NuGet in un progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 3b372b55cbdd8e0e6cc6a6b1089915e0da802489
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-add-package"></a>dotnet add package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet add package`: aggiunge il riferimento al pacchetto in un file di progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory]`

## <a name="description"></a>Descrizione

Il comando `dotnet add package` offre un'opzione utile per aggiungere riferimenti al pacchetto in un file di progetto. Dopo l'esecuzione del comando, viene eseguito un controllo di compatibilità per verificare che il pacchetto sia compatibile con i framework del progetto. Se il controllo ha esito positivo, al file di progetto viene aggiunto un elemento `<PackageReference>` e viene eseguito [dotnet restore](dotnet-restore.md).

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Ad esempio, l'aggiunta di `Newtonsoft.Json` a *ToDo.csproj* determina un output simile all'esempio seguente:

```
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\projects\ToDo\ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 235ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '10.0.3' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

Il file *ToDo.csproj* contiene ora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) per il pacchetto a cui viene fatto riferimento.

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a>Argomenti

`PROJECT`

Specifica il file di progetto. Se non specificato, il comando ne cerca uno nella directory corrente.

`PACKAGE_NAME`

Riferimento al pacchetto da aggiungere.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

`-v|--version <VERSION>`

Versione del pacchetto.

`-f|--framework <FRAMEWORK>`

Aggiunge un riferimento al pacchetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.

`-n|--no-restore`

Aggiunge un riferimento al pacchetto senza eseguire l'anteprima del ripristino e il controllo di compatibilità.

`-s|--source <SOURCE>`

Usa un'origine di pacchetto NuGet specifica durante l'operazione di ripristino.

`--package-directory <PACKAGE_DIRECTORY>`

Ripristina il pacchetto nella directory specificata.

## <a name="examples"></a>Esempi

Aggiungere un pacchetto NuGet `Newtonsoft.Json` in un progetto:

`dotnet add package Newtonsoft.Json`

Aggiungere una versione specifica di un pacchetto in un progetto:

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

Aggiungere un pacchetto usando un'origine NuGet specifica:

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`
