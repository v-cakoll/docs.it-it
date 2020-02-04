---
title: Gestione delle dipendenze negli strumenti di .NET Core
description: Viene illustrato come gestire le dipendenze con gli strumenti di .NET Core.
ms.date: 03/06/2017
ms.openlocfilehash: 916daca0240c10dc63ca96048590a426bc51d450
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965620"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a>Gestire le dipendenze con .NET Core SDK 1,0

Con il passaggio dei progetti .NET Core da project.json a csproj e MSBuild, è stato eseguito un investimento significativo che ha comportato l'unificazione del file di progetto e degli asset che consentono il monitoraggio delle dipendenze. Per i progetti .NET Core, questa operazione è simile a quella di Project. JSON. Non esiste alcun file JSON o XML separato che tiene traccia delle dipendenze NuGet. Con questa modifica, è stato anche introdotto un altro tipo di *riferimento* nella sintassi csproj denominato `<PackageReference>`.

Questo documento descrive il nuovo tipo di riferimento. Illustra anche come aggiungere al progetto una dipendenza del pacchetto usando questo nuovo tipo di riferimento.

## <a name="the-new-packagereference-element"></a>Nuovo elemento \<PackageReference>

L'elemento `<PackageReference>` ha la struttura di base seguente:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Se si ha familiarità con MSBuild, il nuovo elemento risulterà analogo agli altri tipi di riferimento già esistenti. La chiave è l'istruzione `Include`, che specifica l'ID del pacchetto che si desidera aggiungere al progetto. L'elemento figlio `<Version>` specifica la versione da ottenere. Le versioni vengono specificate in base alle [regole della versione di NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Se non si ha familiarità con la sintassi dei file di progetto, vedere la documentazione di riferimento per il [progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) per ulteriori informazioni.

Usare le condizioni per aggiungere una dipendenza disponibile solo in una destinazione specifica, come illustrato nell'esempio seguente:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

La dipendenza sarà valida solo se la compilazione è in corso per la destinazione specificata. Il `$(TargetFramework)` nella condizione è una proprietà di MSBuild che viene impostata nel progetto. Per le applicazioni .NET Core più comuni, non occorre eseguire questa operazione.

## <a name="add-a-dependency-to-the-project"></a>Aggiungere una dipendenza al progetto

L'aggiunta di una dipendenza al progetto è un'operazione semplice. Di seguito è riportato un esempio che illustra come aggiungere Json.NET versione `9.0.1` al progetto. Naturalmente, è applicabile a qualsiasi altra dipendenza NuGet.

Il file di progetto contiene due o più nodi `<ItemGroup>`. In uno dei nodi sono già presenti elementi `<PackageReference>`. È possibile aggiungere la nuova dipendenza a questo nodo o crearne una nuova. il risultato sarà lo stesso.

Nell'esempio seguente viene usato il modello predefinito eliminato da `dotnet new console`. Si tratta di una semplice applicazione console. Quando si apre il progetto, è possibile trovare la `<ItemGroup>` con `<PackageReference>` già esistente. Aggiungere quanto segue:

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

Al termine, salvare il progetto ed eseguire il comando `dotnet restore` per installare la dipendenza.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Il progetto completo è simile al seguente:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="remove-a-dependency-from-the-project"></a>Rimuovere una dipendenza dal progetto

La rimozione di una dipendenza dal file di progetto comporta la semplice rimozione di `<PackageReference>` dal file di progetto.
