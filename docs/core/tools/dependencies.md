---
title: Gestire le dipendenze in .NET Core
description: Viene illustrato come gestire le dipendenze di progetto per un'applicazione .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: b77acc7d4f03a45784f753d3daaa9810f110a6ac
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205945"
---
# <a name="manage-dependencies-in-net-core-applications"></a>Gestire le dipendenze nelle applicazioni .NET Core

Questo articolo illustra come aggiungere e rimuovere dipendenze modificando il file di progetto o usando l'interfaccia della riga di comando.

## <a name="the-packagereference-element"></a>\<Elemento> PackageReference

L' `<PackageReference>` elemento del file di progetto ha la struttura seguente:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

L' `Include` attributo specifica l'ID del pacchetto da aggiungere al progetto. L' `Version` attributo specifica la versione da ottenere. Le versioni vengono specificate in base [alle regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Se non si ha familiarità con la sintassi dei file di progetto, vedere la documentazione di riferimento per il [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per ulteriori informazioni.

Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

La dipendenza nell'esempio precedente sarà valida solo se la compilazione è in corso per la destinazione specificata. `$(TargetFramework)`Nella condizione è una proprietà di MSBuild che viene impostata nel progetto. Per la maggior parte delle applicazioni .NET Core comuni, non è necessario eseguire questa operazione.

## <a name="add-a-dependency-by-editing-the-project-file"></a>Aggiungere una dipendenza modificando il file di progetto

Per aggiungere una dipendenza, aggiungere un `<PackageReference>` elemento all'interno di un `<ItemGroup>` elemento. È possibile aggiungere a un esistente `<ItemGroup>` o crearne uno nuovo. Nell'esempio seguente viene usato il progetto di applicazione console predefinito creato da `dotnet new console` :

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

## <a name="add-a-dependency-by-using-the-cli"></a>Aggiungere una dipendenza usando l'interfaccia della riga di comando

Per aggiungere una dipendenza, eseguire il [dotnet add package](dotnet-add-package.md) comando, come illustrato nell'esempio seguente:

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a>Rimuovere una dipendenza modificando il file di progetto

Per rimuovere una dipendenza, rimuovere il relativo `<PackageReference>` elemento dal file di progetto.

## <a name="remove-a-dependency-by-using-the-cli"></a>Rimuovere una dipendenza usando l'interfaccia della riga di comando

Per rimuovere una dipendenza, eseguire il [dotnet remove package](dotnet-remove-package.md) comando, come illustrato nell'esempio seguente:

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a>Vedere anche

* [Riferimenti ai pacchetti nei file di progetto](../project-sdk/msbuild-props.md#reference-properties-and-items)
* [dotnet list packagecomando](dotnet-remove-package.md)
