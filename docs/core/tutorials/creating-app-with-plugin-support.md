---
title: Creare un'applicazione .NET Core con i plug-in
description: Informazioni su come creare un'applicazione .NET Core che supporta i plug-in.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/28/2019
ms.openlocfilehash: f2997c778b87ecd88c0fd2fadf491763066a4950
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739594"
---
# <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="3d7dd-103">Creare un'applicazione .NET Core con i plug-in</span><span class="sxs-lookup"><span data-stu-id="3d7dd-103">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="3d7dd-104">In questa esercitazione verrà illustrato come:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="3d7dd-105">Strutturare un progetto per il supporto dei plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-105">Structure a project to support plugins.</span></span>
- <span data-ttu-id="3d7dd-106">Creare una classe <xref:System.Runtime.Loader.AssemblyLoadContext> personalizzata per caricare ogni plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-106">Create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load each plugin.</span></span>
- <span data-ttu-id="3d7dd-107">Usare il tipo `System.Runtime.Loader.AssemblyDependencyResolver` per consentire l'uso di plug-in con dipendenze.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-107">Use the `System.Runtime.Loader.AssemblyDependencyResolver` type to allow plugins to have dependencies.</span></span>
- <span data-ttu-id="3d7dd-108">Creare plug-in che possono essere distribuiti con facilità copiando semplicemente gli artefatti di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-108">Author plugins that can be easily deployed by just copying the build artifacts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d7dd-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3d7dd-109">Prerequisites</span></span>

- <span data-ttu-id="3d7dd-110">Installare [.NET Core 3.0 Preview 2 SDK](https://www.microsoft.com/net/core) o una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-110">Install the [.NET Core 3.0 Preview 2 SDK](https://www.microsoft.com/net/core) or a newer version.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="3d7dd-111">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="3d7dd-111">Create the application</span></span>

<span data-ttu-id="3d7dd-112">Il primo passaggio consiste nel creare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-112">The first step is to create the application:</span></span>

1. <span data-ttu-id="3d7dd-113">Creare una nuova cartella ed eseguire `dotnet new console -o AppWithPlugin` nella cartella.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-113">Create a new folder, and in that folder run `dotnet new console -o AppWithPlugin`.</span></span> 
2. <span data-ttu-id="3d7dd-114">Per semplificare la compilazione del progetto, creare un file di soluzione Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-114">To make building the project easier, create a Visual Studio solution file.</span></span> <span data-ttu-id="3d7dd-115">Eseguire `dotnet new sln` nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-115">Run `dotnet new sln` in the same folder.</span></span> 
3. <span data-ttu-id="3d7dd-116">Eseguire `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` per aggiungere il progetto dell'app alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-116">Run `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` to add the app project to the solution.</span></span>

<span data-ttu-id="3d7dd-117">Ora è possibile compilare la struttura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-117">Now we can fill in the skeleton of our application.</span></span> <span data-ttu-id="3d7dd-118">Sostituire il codice nel file *AppWithPlugin/Program.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-118">Replace the code in the *AppWithPlugin/Program.cs* file with the following code:</span></span>

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

## <a name="create-the-plugin-interfaces"></a><span data-ttu-id="3d7dd-119">Creare le interfacce dei plug-in</span><span class="sxs-lookup"><span data-stu-id="3d7dd-119">Create the plugin interfaces</span></span>

<span data-ttu-id="3d7dd-120">Il passaggio successivo della compilazione di un'app con plug-in consiste nel definire l'interfaccia che deve essere implementata dai plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-120">The next step in building an app with plugins is defining the interface the plugins need to implement.</span></span> <span data-ttu-id="3d7dd-121">È consigliabile creare una libreria di classi che contiene tutti i tipi che si prevede di usare per la comunicazione tra l'app e i plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-121">We suggest that you make a class library that contains any types that you plan to use for communicating between your app and plugins.</span></span> <span data-ttu-id="3d7dd-122">Questa divisione consente di pubblicare l'interfaccia del plug-in come pacchetto senza dover distribuire l'applicazione completa.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-122">This division allows you to publish your plugin interface as a package without having to ship your full application.</span></span>

<span data-ttu-id="3d7dd-123">Nella cartella radice del progetto eseguire `dotnet new classlib -o PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-123">In the root folder of the project, run `dotnet new classlib -o PluginBase`.</span></span> <span data-ttu-id="3d7dd-124">Eseguire anche `dotnet sln add PluginBase/PluginBase.csproj` per aggiungere il progetto al file della soluzione.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-124">Also, run `dotnet sln add PluginBase/PluginBase.csproj` to add the project to the solution file.</span></span> <span data-ttu-id="3d7dd-125">Eliminare il file `PluginBase/Class1.cs` e nella cartella `PluginBase` creare un nuovo file denominato `ICommand.cs` con la definizione di interfaccia seguente:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-125">Delete the `PluginBase/Class1.cs` file, and create a new file in the `PluginBase` folder named `ICommand.cs` with the following interface definition:</span></span>

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

<span data-ttu-id="3d7dd-126">Questa interfaccia `ICommand` è l'interfaccia che verrà implementata da tutti i plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-126">This `ICommand` interface is the interface that all of the plugins will implement.</span></span>

<span data-ttu-id="3d7dd-127">Dopo aver definito l'interfaccia `ICommand`, è possibile compilare ulteriormente il progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-127">Now that the `ICommand` interface is defined, the application project can be filled in a little more.</span></span> <span data-ttu-id="3d7dd-128">Aggiungere un riferimento dal progetto `AppWithPlugin` al progetto `PluginBase` con il comando `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` dalla cartella radice.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-128">Add a reference from the `AppWithPlugin` project to the `PluginBase` project with the `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj`  command from the root folder.</span></span>

<span data-ttu-id="3d7dd-129">Sostituire il commento `// Load commands from plugins` con il frammento di codice seguente per abilitare il caricamento dei plug-in dai percorsi di file specificati:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-129">Replace the `// Load commands from plugins` comment with the following code snippet to enable it to load plugins from given file paths:</span></span>

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



<span data-ttu-id="3d7dd-130">Quindi sostituire il commento `// Output the loaded commands` con il frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-130">Then replace the `// Output the loaded commands` comment with the following code snippet:</span></span>

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

<span data-ttu-id="3d7dd-131">Sostituire il commento `// Execute the command with the name passed as an argument` con il frammento seguente:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-131">Replace the `// Execute the command with the name passed as an argument` comment with the following snippet:</span></span>

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

<span data-ttu-id="3d7dd-132">Infine, aggiungere i metodi statici denominati `LoadPlugin` e `CreateCommands` alla classe `Program` come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-132">And finally, add static methods to the `Program` class named `LoadPlugin` and `CreateCommands`, as shown here:</span></span>

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

## <a name="load-plugins"></a><span data-ttu-id="3d7dd-133">Caricare i plug-in</span><span class="sxs-lookup"><span data-stu-id="3d7dd-133">Load plugins</span></span>

<span data-ttu-id="3d7dd-134">A questo punto l'applicazione può caricare e creare un'istanza dei comandi dagli assembly dei plug-in caricati ma non può ancora caricare gli assembly dei plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-134">Now the application can correctly load and instantiate commands from loaded plugin assemblies, but it is still unable to load the plugin assemblies.</span></span> <span data-ttu-id="3d7dd-135">Creare un file denominato *PluginLoadContext.cs* nella cartella *AppWithPlugin* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-135">Create a file named *PluginLoadContext.cs* in the *AppWithPlugin* folder with the following contents:</span></span>

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

<span data-ttu-id="3d7dd-136">Il tipo `PluginLoadContext` deriva da <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-136">The `PluginLoadContext` type derives from <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="3d7dd-137">Il tipo `AssemblyLoadContext` è un tipo speciale nel runtime che consente agli sviluppatori di isolare gli assembly caricati in gruppi diversi per assicurarsi che le versioni degli assembly non entrino in conflitto.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-137">The `AssemblyLoadContext` type is a special type in the runtime that allows developers to isolate loaded assemblies into different groups to ensure that assembly versions do not conflict.</span></span> <span data-ttu-id="3d7dd-138">Inoltre, un tipo `AssemblyLoadContext` personalizzato può scegliere percorsi diversi da cui caricare gli assembly ed eseguire l'override del comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-138">Additionally, a custom `AssemblyLoadContext` can choose different paths to load assemblies from and override the default behavior.</span></span> <span data-ttu-id="3d7dd-139">`PluginLoadContext` usa un'istanza del tipo `AssemblyDependencyResolver` introdotta in .NET Core 3.0 per risolvere i nomi di assembly in percorsi.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-139">The `PluginLoadContext` uses an instance of the `AssemblyDependencyResolver` type introduced in .NET Core 3.0 to resolve assembly names to paths.</span></span> <span data-ttu-id="3d7dd-140">L'oggetto `AssemblyDependencyResolver` è costruito con il percorso per una libreria di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-140">The `AssemblyDependencyResolver` object is constructed with the path to a .NET class library.</span></span> <span data-ttu-id="3d7dd-141">Risolve gli assembly e le librerie native nei relativi percorsi in base al file *deps.json* per la libreria di classi il cui percorso è stato passato al costruttore `AssemblyDependencyResolver`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-141">It resolves assemblies and native libraries to their relative paths based on the *deps.json* file for the class library whose path was passed to the `AssemblyDependencyResolver` constructor.</span></span> <span data-ttu-id="3d7dd-142">Il tipo `AssemblyLoadContext` personalizzato consente ai plug-in di avere proprie dipendenze, mentre l'oggetto `AssemblyDependencyResolver` rende più semplice caricare correttamente le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-142">The custom `AssemblyLoadContext` enables plugins to have their own dependencies, and the `AssemblyDependencyResolver` makes it easy to correctly load the dependencies.</span></span>

<span data-ttu-id="3d7dd-143">Ora che il progetto `AppWithPlugin` ha il tipo `PluginLoadContext`, aggiornare il metodo `Program.LoadPlugin` con il corpo seguente:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-143">Now that the `AppWithPlugin` project has the `PluginLoadContext` type, update the `Program.LoadPlugin` method with the following body:</span></span>

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

<span data-ttu-id="3d7dd-144">Usando un'istanza `PluginLoadContext` diversa per ogni plug-in, i plug-in possono avere dipendenze diverse o persino in conflitto senza problemi.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-144">By using a different `PluginLoadContext` instance for each plugin, the plugins can have different or even conflicting dependencies without issue.</span></span>

## <a name="create-a-simple-plugin-with-no-dependencies"></a><span data-ttu-id="3d7dd-145">Creare un plug-in semplice senza dipendenze</span><span class="sxs-lookup"><span data-stu-id="3d7dd-145">Create a simple plugin with no dependencies</span></span>

<span data-ttu-id="3d7dd-146">Nella cartella radice eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-146">Back in the root folder, do the following:</span></span>

1. <span data-ttu-id="3d7dd-147">Eseguire `dotnet new classlib -o HelloPlugin` per creare un nuovo progetto di libreria di classi denominato `HelloPlugin`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-147">Run `dotnet new classlib -o HelloPlugin` to create a new class library project named `HelloPlugin`.</span></span>
2. <span data-ttu-id="3d7dd-148">Eseguire `dotnet sln add HelloPlugin/HelloPlugin.csproj` per aggiungere il progetto alla soluzione `AppWithPlugin`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-148">Run `dotnet sln add HelloPlugin/HelloPlugin.csproj` to add the project to the `AppWithPlugin` solution.</span></span> 
3. <span data-ttu-id="3d7dd-149">Sostituire il file *HelloPlugin/Class1.cs* con un file denominato *HelloCommand.cs* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-149">Replace the *HelloPlugin/Class1.cs* file with a file named *HelloCommand.cs* with the following contents:</span></span>

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

<span data-ttu-id="3d7dd-150">A questo punto, aprire il file *HelloPlugin.csproj*.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-150">Now, open the *HelloPlugin.csproj* file.</span></span> <span data-ttu-id="3d7dd-151">Il file dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-151">It should look similar to the following:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

<span data-ttu-id="3d7dd-152">Tra i due tag `<Project>` aggiungere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-152">In between the `<Project>` tags, add the following elements:</span></span>

```xml
<ItemGroup>
<ProjectReference Include="..\PluginBase\PluginBase.csproj">
    <Private>false</Private>
</ProjectReference>
</ItemGroup>
```

<span data-ttu-id="3d7dd-153">L'elemento `<Private>false</Private>` è molto importante.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-153">The `<Private>false</Private>` element is very important.</span></span> <span data-ttu-id="3d7dd-154">Indica a MSBuild di non copiare *PluginBase.dll* nella directory di output per HelloPlugin.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-154">This tells MSBuild to not copy *PluginBase.dll* to the output directory for HelloPlugin.</span></span> <span data-ttu-id="3d7dd-155">Se l'assembly *PluginBase.dll* è presente nella directory di output, `PluginLoadContext` individuerà l'assembly e lo caricherà durante il caricamento dell'assembly *HelloPlugin.dll*.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-155">If the *PluginBase.dll* assembly is present in the output directory, `PluginLoadContext` will find the assembly there and load it when it loads the *HelloPlugin.dll* assembly.</span></span> <span data-ttu-id="3d7dd-156">A questo punto, il tipo `HelloPlugin.HelloCommand` implementerà l'interfaccia `ICommand` di *PluginBase.dll* nella directory di output del progetto `HelloPlugin`, non l'interfaccia `ICommand` caricata nel contesto di caricamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-156">At this point, the `HelloPlugin.HelloCommand` type will implement the `ICommand` interface from the *PluginBase.dll* in the output directory of the `HelloPlugin` project, not the `ICommand` interface that is loaded into the default load context.</span></span> <span data-ttu-id="3d7dd-157">Poiché il runtime considera questi due tipi come tipi diversi di assembly differenti, il metodo `AppWithPlugin.Program.CreateCommands` non troverà i comandi.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-157">Since the runtime sees these two types as different types from different assemblies, the `AppWithPlugin.Program.CreateCommands` method will not find the commands.</span></span> <span data-ttu-id="3d7dd-158">Di conseguenza, saranno necessari i metadati `<Private>false</Private>` per il riferimento all'assembly che contiene le interfacce dei plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-158">As a result, the `<Private>false</Private>` metadata is required for the reference to the assembly containing the plugin interfaces.</span></span>

<span data-ttu-id="3d7dd-159">Dopo aver completato il progetto `HelloPlugin`, è necessario aggiornare il progetto `AppWithPlugin` per individuare dove è possibile trovare il plug-in `HelloPlugin`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-159">Now that the `HelloPlugin` project is complete, we should update the `AppWithPlugin` project to know where the `HelloPlugin` plugin can be found.</span></span> <span data-ttu-id="3d7dd-160">Dopo il commento `// Paths to plugins to load`, aggiungere `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` come elemento della matrice `pluginPaths`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-160">After the `// Paths to plugins to load` comment, add `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` as an element of the `pluginPaths` array.</span></span>

## <a name="create-a-plugin-with-library-dependencies"></a><span data-ttu-id="3d7dd-161">Creare un plug-in con dipendenze di libreria</span><span class="sxs-lookup"><span data-stu-id="3d7dd-161">Create a plugin with library dependencies</span></span>

<span data-ttu-id="3d7dd-162">Quasi tutti i plug-in sono più complessi rispetto a un semplice "Hello World" e molti plug-in hanno dipendenze in altre librerie.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-162">Almost all plugins are more complex than a simple "Hello World", and many plugins have dependencies on other libraries.</span></span> <span data-ttu-id="3d7dd-163">I progetti di plug-in `JsonPlugin` e `OldJson` mostrano due esempi di plug-in con dipendenze del pacchetto NuGet in `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-163">The `JsonPlugin` and `OldJson` plugin projects in the sample show two examples of plugins with NuGet package dependencies on `Newtonsoft.Json`.</span></span> <span data-ttu-id="3d7dd-164">I file di progetto non includono informazioni speciali per i riferimenti di progetto e, dopo l'aggiunta dei percorsi dei plug-in alla matrice `pluginPaths`, i plug-in vengono eseguiti correttamente, anche nel caso in cui vengano eseguiti nella stessa esecuzione dell'app AppWithPlugin.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-164">The project files themselves do not have any special information for the project references, and (after adding the plugin paths to the `pluginPaths` array) the plugins run perfectly, even if run in the same execution of the AppWithPlugin app.</span></span> <span data-ttu-id="3d7dd-165">Tuttavia, poiché questi progetti non copiano gli assembly cui viene fatto riferimento nella directory di output, è necessario che gli assembly siano presenti nel computer dell'utente per garantire il funzionamento dei plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-165">However, these projects do not copy the referenced assemblies to their output directory, so the assemblies need to be present on the user's machine for the plugins to work.</span></span> <span data-ttu-id="3d7dd-166">Questo problema può essere risolto in due modi.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-166">There are two ways to work around this problem.</span></span> <span data-ttu-id="3d7dd-167">La prima opzione consiste nell'usare il comando `dotnet publish` per pubblicare la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-167">The first option is to use the `dotnet publish` command to publish the class library.</span></span> <span data-ttu-id="3d7dd-168">In alternativa, se si vuole essere in grado di usare l'output di `dotnet build` per il plug-in, è possibile aggiungere la proprietà `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` tra i due tag `<PropertyGroup>` nel file di progetto del plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-168">Alternatively, if you want to be able to use the output of `dotnet build` for your plugin, you can add the `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` property between the `<PropertyGroup>` tags in the plugin's project file.</span></span> <span data-ttu-id="3d7dd-169">Vedere il progetto di plug-in `XcopyablePlugin` per un esempio.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-169">See the `XcopyablePlugin` plugin project for an example.</span></span>

## <a name="other-plugin-examples-in-the-sample"></a><span data-ttu-id="3d7dd-170">Altri esempi di plug-in</span><span class="sxs-lookup"><span data-stu-id="3d7dd-170">Other plugin examples in the sample</span></span>

<span data-ttu-id="3d7dd-171">L'oggetto `AssemblyDependencyResolver` può anche risolvere le librerie native incluse nei pacchetti NuGet nonché gli assembly satellite localizzati.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-171">The `AssemblyDependencyResolver` object can also resolve native libraries included in NuGet packages as well as localized satellite assemblies.</span></span> <span data-ttu-id="3d7dd-172">Questi scenari sono illustrati rispettivamente da `UVPlugin` e `FrenchPlugin`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-172">The `UVPlugin` and `FrenchPlugin` demonstrate these scenarios respectively.</span></span>

## <a name="how-to-reference-a-plugin-interface-assembly-defined-in-a-nuget-package"></a><span data-ttu-id="3d7dd-173">Come fare riferimento a un assembly di interfaccia di plug-in definito in un pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="3d7dd-173">How to reference a plugin interface assembly defined in a NuGet package</span></span>

<span data-ttu-id="3d7dd-174">Si supponga che sia presente un'app A con un'interfaccia di plug-in definita nel pacchetto NuGet denominato `A.PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-174">Let's say that there is an app A that has a plugin interface defined in the NuGet package named `A.PluginBase`.</span></span> <span data-ttu-id="3d7dd-175">Come fare riferimento correttamente al pacchetto nel progetto di plug-in?</span><span class="sxs-lookup"><span data-stu-id="3d7dd-175">How do you reference the package correctly in your plugin project?</span></span> <span data-ttu-id="3d7dd-176">Per i riferimenti al progetto, l'uso dei metadati `<Private>false</Private>` nell'elemento `ProjectReference` nel file di progetto ha impedito la copia della dll nell'output.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-176">For project references, using the `<Private>false</Private>` metadata on the `ProjectReference` element in the project file prevented the dll from being copied to the output.</span></span>

<span data-ttu-id="3d7dd-177">Per fare riferimento correttamente al pacchetto `A.PluginBase`, si modifica l'elemento `<PackageReference>` nel file di progetto come segue:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-177">To correctly reference the `A.PluginBase` package, you want to change the `<PackageReference>` element in the project file to the following:</span></span>

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

<span data-ttu-id="3d7dd-178">In questo modo si impedisce che gli assembly `A.PluginBase` vengano copiati nella directory di output del plug-in e si garantisce che il plug-in usi la versione A di `A.PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-178">This prevents the `A.PluginBase` assemblies from being copied to the output directory of your plugin and ensures that your plugin will use A's version of `A.PluginBase`.</span></span>

## <a name="plugin-target-framework-recommendations"></a><span data-ttu-id="3d7dd-179">Consigli sul framework di destinazione del plug-in</span><span class="sxs-lookup"><span data-stu-id="3d7dd-179">Plugin target framework recommendations</span></span>

<span data-ttu-id="3d7dd-180">Poiché il caricamento delle dipendenze del plug-in usa il file *deps.json*, tenere presente la raccomandazione relativa al framework di destinazione del plug-in.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-180">Because plugin dependency loading uses the *deps.json* file, there is a gotcha related to the plugin's target framework.</span></span> <span data-ttu-id="3d7dd-181">In particolare, è consigliabile che i plug-in abbiano come destinazione un runtime, ad esempio .NET Core 3.0, anziché una versione di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-181">Specifically, your plugins should target a runtime, such as .NET Core 3.0, instead of a version of .NET Standard.</span></span> <span data-ttu-id="3d7dd-182">Il file `deps.json` viene generato in base al framework di destinazione del progetto e poiché numerosi pacchetti compatibili con .NET Standard offrono assembly di riferimento per la compilazione in .NET Standard e assembly di implementazione per runtime specifici, è possibile che `deps.json` non consideri correttamente gli assembly di implementazione oppure ottenga la versione .NET Standard di un assembly anziché la versione .NET Core prevista.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-182">The `deps.json` file is generated based on which framework the project targets, and since many .NET Standard-compatible packages ship reference assemblies for building against .NET Standard and implementation assemblies for specific runtimes, the `deps.json` may not correctly see implementation assemblies, or it may grab the .NET Standard version of an assembly instead of the .NET Core version you expect.</span></span>
