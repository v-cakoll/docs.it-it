---
title: Framework di destinazione nei progetti di tipo SDK-.NET
description: Informazioni sui framework di destinazione per app e librerie di .NET Core.
ms.date: 12/03/2019
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: 33beb5606cbf857cc41b739f256482b0298f1fb1
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124598"
---
# <a name="target-frameworks-in-sdk-style-projects"></a>Framework di destinazione nei progetti di tipo SDK

Quando si specifica come destinazione un framework in un'app o in una libreria, si specifica il set di API da rendere disponibile all'app o alla libreria. Per specificare il framework di destinazione nel file di progetto, usare i moniker framework di destinazione.

Un'app o una libreria può specificare come destinazione una versione di [.NET Standard](net-standard.md). Le versioni di .NET Standard rappresentano set standardizzati di API in tutte le implementazioni di .NET. Una libreria, ad esempio, può specificare come destinazione .NET Standard 1.6 e ottenere l'accesso ad API che possono essere usate in .NET Core e .NET Framework tramite la stessa codebase.

Un'app o una libreria può anche indicare come destinazione un'implementazione specifica di .NET per ottenere l'accesso ad API specifiche dell'implementazione. Ad esempio, un'app che specifica come destinazione Xamarin.iOS (come `Xamarin.iOS10`) ottiene l'accesso ai wrapper di API iOS forniti da Xamarin per iOS 10 oppure un'app che specifica come destinazione la piattaforma UWP (UWP, `uap10.0`) ottiene l'accesso alle API che consentono la compilazione per dispositivi che eseguono Windows 10.

Per alcuni framework di destinazione, ad esempio .NET Framework, le API vengono definite dagli assembly installati dal framework in un sistema e potrebbero includere API del framework applicazione, ad esempio, ASP.NET.

Per i framework di destinazione basati su pacchetti, ad esempio .NET Standard e .NET Core, le API vengono definite dai pacchetti inclusi nell'app o nella libreria. Un *metapacchetto* è un pacchetto di NuGet che non ha alcun contenuto proprio ma è costituito da un elenco di dipendenze (altri pacchetti). Un framework di destinazione basato su pacchetti NuGet specifica in modo implicito un metapacchetto che fa riferimento a tutti i pacchetti che costituiscono complessivamente il framework.

## <a name="latest-target-framework-versions"></a>Versioni più recenti dei framework di destinazione

La tabella seguente definisce i framework di destinazione più comuni, il modo in cui vengono creati i relativi riferimenti e le versioni [.NET Standard](net-standard.md) implementate da tali pacchetti. Queste versioni di framework di destinazione sono le versioni stabili più recenti. Non sono visualizzate le versioni non definitive. Un moniker framework di destinazione è un formato di token standardizzato per specificare il framework di destinazione di un'app o di una libreria .NET.

| Framework di destinazione      | Ultima versione <br/> Versione stabile | Moniker della versione di .NET Framework di destinazione (TFM, Target Framework Moniker) | Implementato <br/> Versione standard di .NET |
| :-------------------: | :-------------------------: | :----------------------------: | :-------------------------------------: |
| .NET Standard         | 2.1                         | netstandard 2.1                 | N/D                                     |
| .NET Core             | 3.1                         | netcoreapp 3.1                  | 2.1                                     |
| .NET Framework        | 4.8                         | net48                          | 2.0                                     |

## <a name="supported-target-framework-versions"></a>Versioni supportate dei framework di destinazione

Un framework di destinazione viene in genere specificato come riferimento da un moniker framework di destinazione. La tabella seguente mostra i framework di destinazione supportati da .NET Core SDK e dal client NuGet. Gli equivalenti sono visualizzati tra parentesi quadre. Ad esempio, `win81` è un moniker framework di destinazione equivalente a `netcore451`.

| Framework di destinazione           | TFM |
| -------------------------- | --- |
| .NET Standard              | netstandard1.0<br>netstandard1.1<br>netstandard1.2<br>netstandard1.3<br>netstandard1.4<br>netstandard1.5<br>netstandard1.6<br>netstandard2.0<br>netstandard 2.1 |
| .NET Core                  | netcoreapp1.0<br>netcoreapp1.1<br>netcoreapp2.0<br>netcoreapp2.1<br>netcoreapp2.2<br>netcoreapp 3.0<br>netcoreapp 3.1 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Windows Store              | netcore [netcore45]<br>netcore45 [win] [win8]<br>netcore451 [win81] |
| .NET Micro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | wp [wp7]<br>wp7<br>wp75<br>wp8<br>wp81<br>wpa81 |
| Piattaforma UWP (Universal Windows Platform) | uap [uap10.0]<br>uap10.0 [win10] [netcore50] |

## <a name="how-to-specify-target-frameworks"></a>Come specificare framework di destinazione

I framework di destinazione sono specificati nel file di progetto. Quando viene specificato un singolo framework di destinazione, usare l'elemento **TargetFramework**. Il file di progetto di app console seguente illustra come definire come destinazione .NET Core 3,0:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Quando si specificano più framework di destinazione, è possibile fare riferimento in modo condizionale agli assembly per ogni framework di destinazione. Nel codice è possibile eseguire in modo condizionale la compilazione con tali assembly usando i simboli del preprocessore con logica *if-then-else*.

Il file di progetto della libreria seguente specifica come destinazione le API di .NET Standard (`netstandard1.4`) e le API di .NET Framework (`net40` e `net45`). Usare l'elemento **TargetFrameworks** plurale con più framework di destinazione. Si noti che gli attributi `Condition` includono pacchetti specifici dell'implementazione quando la libreria viene compilata per i due moniker framework di destinazione di .NET Framework:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

Nella libreria o nell'app scrivere codice condizionale per la compilazione per ogni framework di destinazione:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45  
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

Il sistema di compilazione è in grado di riconoscere i simboli del preprocessore che rappresentano i Framework di destinazione mostrati nella tabella [versioni di destinazione supportate](#supported-target-framework-versions) quando si usano progetti in stile SDK. Quando si usa un simbolo che rappresenta un moniker framework di destinazione di .NET Standard o .NET Core, sostituire il punto con un carattere di sottolineatura e sostituire le lettere minuscole con lettere maiuscole, ad esempio il simbolo per `netstandard1.4` è `NETSTANDARD1_4`).

L'elenco completo di simboli del preprocessore per il framework di destinazione di .NET Core è:

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>Framework di destinazione deprecati

I framework di destinazione seguenti sono deprecati. I pacchetti che hanno come destinazione questi framework di destinazione devono essere migrati alle sostituzioni indicate.

| Moniker framework di destinazione deprecati                                                                             | Sostituzione |
| ------------------------------------------------------------------------------------------ | ----------- |
| aspnet50<br>aspnetcore50<br>dnxcore50<br>dnx<br>dnx45<br>dnx451<br>dnx452                  | netcoreapp  |
| dotnet<br>dotnet50<br>dotnet51<br>dotnet52<br>dotnet53<br>dotnet54<br>dotnet55<br>dotnet56 | netstandard |
| netcore50                                                                                  | uap10.0     |
| win                                                                                        | netcore45   |
| win8                                                                                       | netcore45   |
| win81                                                                                      | netcore451  |
| win10                                                                                      | uap10.0     |
| winrt                                                                                      | netcore45   |

## <a name="see-also"></a>Vedere anche

- [Pacchetti, metapacchetti e framework](../core/packages.md)
- [Sviluppo di librerie con strumenti multipiattaforma](../core/tutorials/libraries.md)
- [.NET Standard](net-standard.md)
- [Controllo delle versioni di .NET Core](../core/versions/index.md)
- [dotnet/standard GitHub repository](https://github.com/dotnet/standard) (Repository dotnet/standard di GitHub)
- [NuGet Tools GitHub Repository](https://github.com/joelverhagen/NuGetTools) (Repository di GitHub per strumenti NuGet)
- [Framework Profiles in .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html) (Profili di framework in .NET)
