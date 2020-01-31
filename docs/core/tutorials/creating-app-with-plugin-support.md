---
title: Creare un'applicazione .NET Core con i plug-in
description: Informazioni su come creare un'applicazione .NET Core che supporta i plug-in.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 10/16/2019
ms.openlocfilehash: 32205a507bc95b2f8a2f75368aab3fde710249ee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787846"
---
# <a name="create-a-net-core-application-with-plugins"></a>Creare un'applicazione .NET Core con i plug-in

Questa esercitazione illustra come creare un <xref:System.Runtime.Loader.AssemblyLoadContext> personalizzato per caricare i plug-in. Viene usato un <xref:System.Runtime.Loader.AssemblyDependencyResolver> per risolvere le dipendenze del plug-in. L'esercitazione isola correttamente le dipendenze del plug-in dall'applicazione host. Si imparerà a eseguire le operazioni seguenti:

- Strutturare un progetto per il supporto dei plug-in.
- Creare una classe <xref:System.Runtime.Loader.AssemblyLoadContext> personalizzata per caricare ogni plug-in.
- Usare il tipo <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> per consentire l'uso di plug-in con dipendenze.
- Creare plug-in che possono essere distribuiti con facilità copiando semplicemente gli artefatti di compilazione.

## <a name="prerequisites"></a>Prerequisiti

- Installare [.NET Core 3,0 SDK](https://dotnet.microsoft.com/download) o una versione più recente.

## <a name="create-the-application"></a>Creare l'applicazione

Il primo passaggio consiste nel creare l'applicazione:

1. Creare una nuova cartella e in tale cartella eseguire il comando seguente:

    ```dotnetcli
    dotnet new console -o AppWithPlugin
    ```

2. Per semplificare la compilazione del progetto, creare un file di soluzione di Visual Studio nella stessa cartella. Eseguire il comando seguente:

    ```dotnetcli
    dotnet new sln
    ```

3. Eseguire il comando seguente per aggiungere il progetto di app alla soluzione:

    ```dotnetcli
    dotnet sln add AppWithPlugin/AppWithPlugin.csproj
    ```

Ora è possibile compilare la struttura dell'applicazione. Sostituire il codice nel file *AppWithPlugin/Program.cs* con il codice seguente:

```csharp
using PluginBase;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Reflection;

namespace AppWithPlugin
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                if (args.Length == 1 && args[0] == "/d")
                {
                    Console.WriteLine("Waiting for any key...");
                    Console.ReadLine();
                }

                // Load commands from plugins.

                if (args.Length == 0)
                {
                    Console.WriteLine("Commands: ");
                    // Output the loaded commands.
                }
                else
                {
                    foreach (string commandName in args)
                    {
                        Console.WriteLine($"-- {commandName} --");

                        // Execute the command with the name passed as an argument.

                        Console.WriteLine();
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex);
            }
        }
    }
}

```

## <a name="create-the-plugin-interfaces"></a>Creare le interfacce dei plug-in

Il passaggio successivo della compilazione di un'app con plug-in consiste nel definire l'interfaccia che deve essere implementata dai plug-in. È consigliabile creare una libreria di classi che contiene tutti i tipi che si prevede di usare per la comunicazione tra l'app e i plug-in. Questa divisione consente di pubblicare l'interfaccia del plug-in come pacchetto senza dover distribuire l'applicazione completa.

Nella cartella radice del progetto eseguire `dotnet new classlib -o PluginBase`. Eseguire anche `dotnet sln add PluginBase/PluginBase.csproj` per aggiungere il progetto al file della soluzione. Eliminare il file `PluginBase/Class1.cs` e nella cartella `PluginBase` creare un nuovo file denominato `ICommand.cs` con la definizione di interfaccia seguente:

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

Questa interfaccia `ICommand` è l'interfaccia che verrà implementata da tutti i plug-in.

Dopo aver definito l'interfaccia `ICommand`, è possibile compilare ulteriormente il progetto dell'applicazione. Aggiungere un riferimento dal progetto `AppWithPlugin` al progetto `PluginBase` con il comando `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` dalla cartella radice.

Sostituire il commento `// Load commands from plugins` con il frammento di codice seguente per abilitare il caricamento dei plug-in dai percorsi di file specificati:

```csharp
string[] pluginPaths = new string[]
{
    // Paths to plugins to load.
};

IEnumerable<ICommand> commands = pluginPaths.SelectMany(pluginPath =>
{
    Assembly pluginAssembly = LoadPlugin(pluginPath);
    return CreateCommands(pluginAssembly);
}).ToList();
```

Quindi sostituire il commento `// Output the loaded commands` con il frammento di codice seguente:

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

Sostituire il commento `// Execute the command with the name passed as an argument` con il frammento seguente:

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

Infine, aggiungere i metodi statici denominati `LoadPlugin` e `CreateCommands` alla classe `Program` come illustrato di seguito:

```csharp
static Assembly LoadPlugin(string relativePath)
{
    throw new NotImplementedException();
}

static IEnumerable<ICommand> CreateCommands(Assembly assembly)
{
    int count = 0;

    foreach (Type type in assembly.GetTypes())
    {
        if (typeof(ICommand).IsAssignableFrom(type))
        {
            ICommand result = Activator.CreateInstance(type) as ICommand;
            if (result != null)
            {
                count++;
                yield return result;
            }
        }
    }

    if (count == 0)
    {
        string availableTypes = string.Join(",", assembly.GetTypes().Select(t => t.FullName));
        throw new ApplicationException(
            $"Can't find any type which implements ICommand in {assembly} from {assembly.Location}.\n" +
            $"Available types: {availableTypes}");
    }
}
```

## <a name="load-plugins"></a>Caricare i plug-in

A questo punto l'applicazione è in grado di caricare e creare istanze di comandi da assembly di plug-in caricati, ma non è ancora in grado di caricare gli assembly del plug-in Creare un file denominato *PluginLoadContext.cs* nella cartella *AppWithPlugin* con il contenuto seguente:

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

Il tipo `PluginLoadContext` deriva da <xref:System.Runtime.Loader.AssemblyLoadContext>. Il tipo di `AssemblyLoadContext` è un tipo speciale nel runtime che consente agli sviluppatori di isolare gli assembly caricati in gruppi diversi per garantire che le versioni degli assembly non siano in conflitto. Inoltre, un tipo `AssemblyLoadContext` personalizzato può scegliere percorsi diversi da cui caricare gli assembly ed eseguire l'override del comportamento predefinito. `PluginLoadContext` usa un'istanza del tipo `AssemblyDependencyResolver` introdotta in .NET Core 3.0 per risolvere i nomi di assembly in percorsi. L'oggetto `AssemblyDependencyResolver` è costruito con il percorso per una libreria di classi .NET. Risolve gli assembly e le librerie native nei relativi percorsi in base al file *deps.json* per la libreria di classi il cui percorso è stato passato al costruttore `AssemblyDependencyResolver`. Il tipo `AssemblyLoadContext` personalizzato consente ai plug-in di avere proprie dipendenze, mentre l'oggetto `AssemblyDependencyResolver` rende più semplice caricare correttamente le dipendenze.

Ora che il progetto `AppWithPlugin` ha il tipo `PluginLoadContext`, aggiornare il metodo `Program.LoadPlugin` con il corpo seguente:

```csharp
static Assembly LoadPlugin(string relativePath)
{
    // Navigate up to the solution root
    string root = Path.GetFullPath(Path.Combine(
        Path.GetDirectoryName(
            Path.GetDirectoryName(
                Path.GetDirectoryName(
                    Path.GetDirectoryName(
                        Path.GetDirectoryName(typeof(Program).Assembly.Location)))))));

    string pluginLocation = Path.GetFullPath(Path.Combine(root, relativePath.Replace('\\', Path.DirectorySeparatorChar)));
    Console.WriteLine($"Loading commands from: {pluginLocation}");
    PluginLoadContext loadContext = new PluginLoadContext(pluginLocation);
    return loadContext.LoadFromAssemblyName(new AssemblyName(Path.GetFileNameWithoutExtension(pluginLocation)));
}
```

Usando un'istanza `PluginLoadContext` diversa per ogni plug-in, i plug-in possono avere dipendenze diverse o persino in conflitto senza problemi.

## <a name="simple-plugin-with-no-dependencies"></a>Plug-in semplice senza dipendenze

Nella cartella radice eseguire le operazioni seguenti:

1. Eseguire il comando seguente per creare un nuovo progetto di libreria di classi denominato `HelloPlugin`:
    
    ```dotnetcli
    dotnet new classlib -o HelloPlugin
    ```

2. Eseguire il comando seguente per aggiungere il progetto alla soluzione `AppWithPlugin`:

    ```dotnetcli
    dotnet sln add HelloPlugin/HelloPlugin.csproj
    ```

3. Sostituire il file *HelloPlugin/Class1.cs* con un file denominato *HelloCommand.cs* con il contenuto seguente:

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

A questo punto, aprire il file *HelloPlugin.csproj*. Il file dovrebbe essere simile al seguente:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

Tra i due tag `<Project>` aggiungere gli elementi seguenti:

```xml
<ItemGroup>
    <ProjectReference Include="..\PluginBase\PluginBase.csproj">
        <Private>false</Private>
        <ExcludeAssets>runtime</ExcludeAssets>
    </ProjectReference>
</ItemGroup>
```

L'elemento `<Private>false</Private>` è importante. Indica a MSBuild di non copiare *PluginBase.dll* nella directory di output per HelloPlugin. Se l'assembly *PluginBase.dll* è presente nella directory di output, `PluginLoadContext` individuerà l'assembly e lo caricherà durante il caricamento dell'assembly *HelloPlugin.dll*. A questo punto, il tipo `HelloPlugin.HelloCommand` implementerà l'interfaccia `ICommand` di *PluginBase.dll* nella directory di output del progetto `HelloPlugin`, non l'interfaccia `ICommand` caricata nel contesto di caricamento predefinito. Poiché il runtime Visualizza questi due tipi come tipi diversi da assembly diversi, il metodo `AppWithPlugin.Program.CreateCommands` non troverà i comandi. Di conseguenza, saranno necessari i metadati `<Private>false</Private>` per il riferimento all'assembly che contiene le interfacce dei plug-in.

Analogamente, anche l'elemento `<ExcludeAssets>runtime</ExcludeAssets>` è importante se il `PluginBase` fa riferimento ad altri pacchetti. Questa impostazione ha lo stesso effetto di `<Private>false</Private>` ma funziona sui riferimenti ai pacchetti che possono essere inclusi nel progetto `PluginBase` o in una delle relative dipendenze.

Ora che il progetto `HelloPlugin` è completo, è necessario aggiornare il progetto `AppWithPlugin` per capire dove è possibile trovare il plug-in `HelloPlugin`. Dopo il commento `// Paths to plugins to load`, aggiungere `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` come elemento della matrice `pluginPaths`.

## <a name="plugin-with-library-dependencies"></a>Plug-in con dipendenze di libreria

Quasi tutti i plug-in sono più complessi rispetto a un semplice "Hello World" e molti plug-in hanno dipendenze in altre librerie. I progetti di plug-in `JsonPlugin` e `OldJson` mostrano due esempi di plug-in con dipendenze del pacchetto NuGet in `Newtonsoft.Json`. I file di progetto non dispongono di informazioni speciali per i riferimenti al progetto e (dopo aver aggiunto i percorsi del plug-in all'array `pluginPaths`) i plug-in vengono eseguiti perfettamente, anche se vengono eseguiti nella stessa esecuzione dell'app AppWithPlugin. Tuttavia, questi progetti non copiano gli assembly a cui si fa riferimento nella directory di output, quindi gli assembly devono essere presenti nel computer dell'utente per consentire il funzionamento dei plug-in. Questo problema può essere risolto in due modi. La prima opzione consiste nell'usare il comando `dotnet publish` per pubblicare la libreria di classi. In alternativa, se si vuole essere in grado di usare l'output di `dotnet build` per il plug-in, è possibile aggiungere la proprietà `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` tra i due tag `<PropertyGroup>` nel file di progetto del plug-in. Vedere il progetto di plug-in `XcopyablePlugin` per un esempio.

## <a name="other-examples-in-the-sample"></a>Altri esempi nell'esempio

Il codice sorgente completo per questa esercitazione è reperibile nel [repository dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin). L'esempio completato include alcuni altri esempi del comportamento di `AssemblyDependencyResolver`. Ad esempio, l'oggetto `AssemblyDependencyResolver` può anche risolvere le librerie native nonché gli assembly satellite localizzati inclusi nei pacchetti NuGet. `UVPlugin` e `FrenchPlugin` nel repository degli esempi illustrano questi scenari.

## <a name="reference-a-plugin-interface-from-a-nuget-package"></a>Fare riferimento a un'interfaccia del plug-in da un pacchetto NuGet

Si supponga che sia presente un'app A con un'interfaccia di plug-in definita nel pacchetto NuGet denominato `A.PluginBase`. Come fare riferimento correttamente al pacchetto nel progetto di plug-in? Per i riferimenti al progetto, l'uso dei metadati `<Private>false</Private>` nell'elemento `ProjectReference` nel file di progetto ha impedito la copia della dll nell'output.

Per fare riferimento correttamente al pacchetto `A.PluginBase`, si modifica l'elemento `<PackageReference>` nel file di progetto come segue:

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

In questo modo si impedisce che gli assembly `A.PluginBase` vengano copiati nella directory di output del plug-in e si garantisce che il plug-in usi la versione A di `A.PluginBase`.

## <a name="plugin-target-framework-recommendations"></a>Consigli sul framework di destinazione del plug-in

Poiché il caricamento delle dipendenze del plug-in usa il file *deps.json*, tenere presente la raccomandazione relativa al framework di destinazione del plug-in. In particolare, è consigliabile che i plug-in abbiano come destinazione un runtime, ad esempio .NET Core 3.0, anziché una versione di .NET Standard. Il file *.deps.json* viene generato in base al framework di destinazione del progetto e poiché numerosi pacchetti compatibili con .NET Standard offrono assembly di riferimento per la compilazione in .NET Standard e assembly di implementazione per runtime specifici, è possibile che *.deps.json* non consideri correttamente gli assembly di implementazione oppure ottenga la versione .NET Standard di un assembly anziché la versione .NET Core prevista.

## <a name="plugin-framework-references"></a>Riferimenti al Framework di plug-in

Attualmente, i plug-in non possono introdurre nuovi Framework nel processo. Ad esempio, non è possibile caricare un plug-in che usa il Framework di `Microsoft.AspNetCore.App` in un'applicazione che usa solo il Framework `Microsoft.NETCore.App` radice. L'applicazione host deve dichiarare i riferimenti a tutti i Framework necessari per i plug-in.
