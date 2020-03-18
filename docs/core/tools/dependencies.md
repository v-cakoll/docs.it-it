---
title: Gestire le dipendenze in .NET CoreManage dependencies in .NET Core
description: Viene illustrato come gestire le dipendenze di progetto per un'applicazione .NET Core.Explains how to manage project dependencies for a .NET Core application.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 367be7eb04d58bffc0846de1d035a5801e8d9376
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399147"
---
# <a name="manage-dependencies-in-net-core-applications"></a>Gestire le dipendenze nelle applicazioni .NET CoreManage dependencies in .NET Core applications

In questo articolo viene illustrato come aggiungere e rimuovere dipendenze modificando il file di progetto o utilizzando l'interfaccia della riga di comando.

## <a name="the-packagereference-element"></a>Elemento \<del> PackageReferenceThe PackageReference> element

L'elemento del file di progetto ha la struttura seguente:The `<PackageReference>` project file element has the following structure:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

L'attributo `Include` specifica l'ID del pacchetto da aggiungere al progetto. L'attributo `Version` specifica la versione da ottenere. Le versioni vengono specificate in base alle regole della [versione NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Se non si ha familiarità con la sintassi del file di progetto, vedere la documentazione di riferimento del [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per altre informazioni.

Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:Use conditions to add a dependency that's available only in a specific target, as shown in the following example:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

La dipendenza nell'esempio precedente sarà valida solo se la compilazione viene eseguito per quella destinazione specificata. La `$(TargetFramework)` condizione nella condizione è una proprietà MSBuild che viene impostata nel progetto. Per le applicazioni .NET Core più comuni, non è necessario eseguire questa operazione.

## <a name="add-a-dependency-by-editing-the-project-file"></a>Aggiungere una dipendenza modificando il file di progettoAdd a dependency by editing the project file

Per aggiungere una dipendenza, `<PackageReference>` aggiungere `<ItemGroup>` un elemento all'interno di un elemento. È possibile aggiungere `<ItemGroup>` a un esistente o crearne uno nuovo. Nell'esempio seguente viene utilizzato il progetto `dotnet new console`di applicazione console predefinito creato da :

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a>Aggiungere una dipendenza utilizzando l'interfaccia della riga di comandoAdd a dependency by using the CLI

Per aggiungere una dipendenza, [dotnet add package](dotnet-add-package.md) eseguire il comando, come illustrato nell'esempio seguente:To add a dependency, run the command, as shown in the following example:

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a>Rimuovere una dipendenza modificando il file di progetto

Per rimuovere una dipendenza, `<PackageReference>` rimuovere il relativo elemento dal file di progetto.

## <a name="remove-a-dependency-by-using-the-cli"></a>Rimuovere una dipendenza utilizzando l'interfaccia della riga di comando

Per rimuovere una dipendenza, [dotnet remove package](dotnet-remove-package.md) eseguire il comando, come illustrato nell'esempio seguente:To remove a dependency, run the command, as shown in the following example:

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a>Vedere anche

* [Pacchetti NuGet nei file di progettoNuGet packages in project files](../project-sdk/msbuild-props.md#nuget-packages)
* [dotnet list packageComando](dotnet-remove-package.md)
