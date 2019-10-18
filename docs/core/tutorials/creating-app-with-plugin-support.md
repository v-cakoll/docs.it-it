---
title: Creare un'applicazione .NET Core con i plug-in
description: Informazioni su come creare un'applicazione .NET Core che supporta i plug-in.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 10/16/2019
ms.openlocfilehash: 92c219817ad27fbc906ee3778d3f5372d61151ac
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523203"
---
# <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="c03ce-103">Creare un'applicazione .NET Core con i plug-in</span><span class="sxs-lookup"><span data-stu-id="c03ce-103">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="c03ce-104">Questa esercitazione illustra come creare un <xref:System.Runtime.Loader.AssemblyLoadContext> personalizzato per caricare i plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-104">This tutorial shows you how to create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load plugins.</span></span> <span data-ttu-id="c03ce-105">Viene usato un <xref:System.Runtime.Loader.AssemblyDependencyResolver> per risolvere le dipendenze del plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-105">An <xref:System.Runtime.Loader.AssemblyDependencyResolver> is used to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="c03ce-106">L'esercitazione isola correttamente le dipendenze del plug-in dall'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="c03ce-106">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span> <span data-ttu-id="c03ce-107">Si imparerà a eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c03ce-107">You'll learn how to:</span></span>

- <span data-ttu-id="c03ce-108">Strutturare un progetto per il supporto dei plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-108">Structure a project to support plugins.</span></span>
- <span data-ttu-id="c03ce-109">Creare una classe <xref:System.Runtime.Loader.AssemblyLoadContext> personalizzata per caricare ogni plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-109">Create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load each plugin.</span></span>
- <span data-ttu-id="c03ce-110">Usare il tipo <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> per consentire l'uso di plug-in con dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c03ce-110">Use the <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> type to allow plugins to have dependencies.</span></span>
- <span data-ttu-id="c03ce-111">Creare plug-in che possono essere distribuiti con facilità copiando semplicemente gli artefatti di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c03ce-111">Author plugins that can be easily deployed by just copying the build artifacts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c03ce-112">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="c03ce-112">Prerequisites</span></span>

- <span data-ttu-id="c03ce-113">Installare [.NET Core 3,0](https://dotnet.microsoft.com/download) o una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="c03ce-113">Install the [.NET Core 3.0](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="c03ce-114">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="c03ce-114">Create the application</span></span>

<span data-ttu-id="c03ce-115">Il primo passaggio consiste nel creare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="c03ce-115">The first step is to create the application:</span></span>

1. <span data-ttu-id="c03ce-116">Creare una nuova cartella e in tale cartella eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-116">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new console -o AppWithPlugin
    ```

2. <span data-ttu-id="c03ce-117">Per semplificare la compilazione del progetto, creare un file di soluzione di Visual Studio nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="c03ce-117">To make building the project easier, create a Visual Studio solution file in the same folder.</span></span> <span data-ttu-id="c03ce-118">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-118">Run the following command:</span></span>

    ```dotnetcli
    dotnet new sln
    ```

3. <span data-ttu-id="c03ce-119">Eseguire il comando seguente per aggiungere il progetto di app alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="c03ce-119">Run the following command to add the app project to the solution:</span></span>

    ```dotnetcli
    dotnet sln add AppWithPlugin/AppWithPlugin.csproj
    ```

<span data-ttu-id="c03ce-120">Ora è possibile compilare la struttura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c03ce-120">Now we can fill in the skeleton of our application.</span></span> <span data-ttu-id="c03ce-121">Sostituire il codice nel file *AppWithPlugin/Program.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-121">Replace the code in the *AppWithPlugin/Program.cs* file with the following code:</span></span>

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

## <a name="create-the-plugin-interfaces"></a><span data-ttu-id="c03ce-122">Creare le interfacce dei plug-in</span><span class="sxs-lookup"><span data-stu-id="c03ce-122">Create the plugin interfaces</span></span>

<span data-ttu-id="c03ce-123">Il passaggio successivo della compilazione di un'app con plug-in consiste nel definire l'interfaccia che deve essere implementata dai plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-123">The next step in building an app with plugins is defining the interface the plugins need to implement.</span></span> <span data-ttu-id="c03ce-124">È consigliabile creare una libreria di classi che contiene tutti i tipi che si prevede di usare per la comunicazione tra l'app e i plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-124">We suggest that you make a class library that contains any types that you plan to use for communicating between your app and plugins.</span></span> <span data-ttu-id="c03ce-125">Questa divisione consente di pubblicare l'interfaccia del plug-in come pacchetto senza dover distribuire l'applicazione completa.</span><span class="sxs-lookup"><span data-stu-id="c03ce-125">This division allows you to publish your plugin interface as a package without having to ship your full application.</span></span>

<span data-ttu-id="c03ce-126">Nella cartella radice del progetto eseguire `dotnet new classlib -o PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="c03ce-126">In the root folder of the project, run `dotnet new classlib -o PluginBase`.</span></span> <span data-ttu-id="c03ce-127">Eseguire anche `dotnet sln add PluginBase/PluginBase.csproj` per aggiungere il progetto al file della soluzione.</span><span class="sxs-lookup"><span data-stu-id="c03ce-127">Also, run `dotnet sln add PluginBase/PluginBase.csproj` to add the project to the solution file.</span></span> <span data-ttu-id="c03ce-128">Eliminare il file `PluginBase/Class1.cs` e nella cartella `PluginBase` creare un nuovo file denominato `ICommand.cs` con la definizione di interfaccia seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-128">Delete the `PluginBase/Class1.cs` file, and create a new file in the `PluginBase` folder named `ICommand.cs` with the following interface definition:</span></span>

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

<span data-ttu-id="c03ce-129">Questa interfaccia `ICommand` è l'interfaccia che verrà implementata da tutti i plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-129">This `ICommand` interface is the interface that all of the plugins will implement.</span></span>

<span data-ttu-id="c03ce-130">Dopo aver definito l'interfaccia `ICommand`, è possibile compilare ulteriormente il progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c03ce-130">Now that the `ICommand` interface is defined, the application project can be filled in a little more.</span></span> <span data-ttu-id="c03ce-131">Aggiungere un riferimento dal progetto `AppWithPlugin` al progetto `PluginBase` con il comando `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` dalla cartella radice.</span><span class="sxs-lookup"><span data-stu-id="c03ce-131">Add a reference from the `AppWithPlugin` project to the `PluginBase` project with the `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj`  command from the root folder.</span></span>

<span data-ttu-id="c03ce-132">Sostituire il commento `// Load commands from plugins` con il frammento di codice seguente per abilitare il caricamento dei plug-in dai percorsi di file specificati:</span><span class="sxs-lookup"><span data-stu-id="c03ce-132">Replace the `// Load commands from plugins` comment with the following code snippet to enable it to load plugins from given file paths:</span></span>

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

<span data-ttu-id="c03ce-133">Quindi sostituire il commento `// Output the loaded commands` con il frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-133">Then replace the `// Output the loaded commands` comment with the following code snippet:</span></span>

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

<span data-ttu-id="c03ce-134">Sostituire il commento `// Execute the command with the name passed as an argument` con il frammento seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-134">Replace the `// Execute the command with the name passed as an argument` comment with the following snippet:</span></span>

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

<span data-ttu-id="c03ce-135">Infine, aggiungere i metodi statici denominati `LoadPlugin` e `CreateCommands` alla classe `Program` come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c03ce-135">And finally, add static methods to the `Program` class named `LoadPlugin` and `CreateCommands`, as shown here:</span></span>

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

## <a name="load-plugins"></a><span data-ttu-id="c03ce-136">Caricare i plug-in</span><span class="sxs-lookup"><span data-stu-id="c03ce-136">Load plugins</span></span>

<span data-ttu-id="c03ce-137">A questo punto l'applicazione è in grado di caricare e creare istanze di comandi da assembly di plug-in caricati, ma non è ancora in grado di caricare gli assembly del plug-in</span><span class="sxs-lookup"><span data-stu-id="c03ce-137">Now the application can correctly load and instantiate commands from loaded plugin assemblies, but it's still unable to load the plugin assemblies.</span></span> <span data-ttu-id="c03ce-138">Creare un file denominato *PluginLoadContext.cs* nella cartella *AppWithPlugin* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-138">Create a file named *PluginLoadContext.cs* in the *AppWithPlugin* folder with the following contents:</span></span>

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

<span data-ttu-id="c03ce-139">Il tipo `PluginLoadContext` deriva da <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="c03ce-139">The `PluginLoadContext` type derives from <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="c03ce-140">Il tipo di `AssemblyLoadContext` è un tipo speciale nel runtime che consente agli sviluppatori di isolare gli assembly caricati in gruppi diversi per garantire che le versioni degli assembly non siano in conflitto.</span><span class="sxs-lookup"><span data-stu-id="c03ce-140">The `AssemblyLoadContext` type is a special type in the runtime that allows developers to isolate loaded assemblies into different groups to ensure that assembly versions don't conflict.</span></span> <span data-ttu-id="c03ce-141">Inoltre, un tipo `AssemblyLoadContext` personalizzato può scegliere percorsi diversi da cui caricare gli assembly ed eseguire l'override del comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="c03ce-141">Additionally, a custom `AssemblyLoadContext` can choose different paths to load assemblies from and override the default behavior.</span></span> <span data-ttu-id="c03ce-142">`PluginLoadContext` usa un'istanza del tipo `AssemblyDependencyResolver` introdotta in .NET Core 3.0 per risolvere i nomi di assembly in percorsi.</span><span class="sxs-lookup"><span data-stu-id="c03ce-142">The `PluginLoadContext` uses an instance of the `AssemblyDependencyResolver` type introduced in .NET Core 3.0 to resolve assembly names to paths.</span></span> <span data-ttu-id="c03ce-143">L'oggetto `AssemblyDependencyResolver` è costruito con il percorso per una libreria di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="c03ce-143">The `AssemblyDependencyResolver` object is constructed with the path to a .NET class library.</span></span> <span data-ttu-id="c03ce-144">Risolve gli assembly e le librerie native nei relativi percorsi in base al file *deps.json* per la libreria di classi il cui percorso è stato passato al costruttore `AssemblyDependencyResolver`.</span><span class="sxs-lookup"><span data-stu-id="c03ce-144">It resolves assemblies and native libraries to their relative paths based on the *.deps.json* file for the class library whose path was passed to the `AssemblyDependencyResolver` constructor.</span></span> <span data-ttu-id="c03ce-145">Il tipo `AssemblyLoadContext` personalizzato consente ai plug-in di avere proprie dipendenze, mentre l'oggetto `AssemblyDependencyResolver` rende più semplice caricare correttamente le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c03ce-145">The custom `AssemblyLoadContext` enables plugins to have their own dependencies, and the `AssemblyDependencyResolver` makes it easy to correctly load the dependencies.</span></span>

<span data-ttu-id="c03ce-146">Ora che il progetto `AppWithPlugin` ha il tipo `PluginLoadContext`, aggiornare il metodo `Program.LoadPlugin` con il corpo seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-146">Now that the `AppWithPlugin` project has the `PluginLoadContext` type, update the `Program.LoadPlugin` method with the following body:</span></span>

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

<span data-ttu-id="c03ce-147">Usando un'istanza `PluginLoadContext` diversa per ogni plug-in, i plug-in possono avere dipendenze diverse o persino in conflitto senza problemi.</span><span class="sxs-lookup"><span data-stu-id="c03ce-147">By using a different `PluginLoadContext` instance for each plugin, the plugins can have different or even conflicting dependencies without issue.</span></span>

## <a name="simple-plugin-with-no-dependencies"></a><span data-ttu-id="c03ce-148">Plug-in semplice senza dipendenze</span><span class="sxs-lookup"><span data-stu-id="c03ce-148">Simple plugin with no dependencies</span></span>

<span data-ttu-id="c03ce-149">Nella cartella radice eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c03ce-149">Back in the root folder, do the following:</span></span>

1. <span data-ttu-id="c03ce-150">Eseguire il comando seguente per creare un nuovo progetto di libreria di classi denominato `HelloPlugin`:</span><span class="sxs-lookup"><span data-stu-id="c03ce-150">Run the following command to create a new class library project named `HelloPlugin`:</span></span>
    
    ```dotnetcli
    dotnet new classlib -o HelloPlugin
    ```

2. <span data-ttu-id="c03ce-151">Eseguire il comando seguente per aggiungere il progetto alla soluzione `AppWithPlugin`:</span><span class="sxs-lookup"><span data-stu-id="c03ce-151">Run the following command to add the project to the `AppWithPlugin` solution:</span></span>

    ```dotnetcli
    dotnet sln add HelloPlugin/HelloPlugin.csproj
    ```

3. <span data-ttu-id="c03ce-152">Sostituire il file *HelloPlugin/Class1.cs* con un file denominato *HelloCommand.cs* con il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-152">Replace the *HelloPlugin/Class1.cs* file with a file named *HelloCommand.cs* with the following contents:</span></span>

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

<span data-ttu-id="c03ce-153">A questo punto, aprire il file *HelloPlugin.csproj*.</span><span class="sxs-lookup"><span data-stu-id="c03ce-153">Now, open the *HelloPlugin.csproj* file.</span></span> <span data-ttu-id="c03ce-154">Il file dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c03ce-154">It should look similar to the following:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

<span data-ttu-id="c03ce-155">Tra i due tag `<Project>` aggiungere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c03ce-155">In between the `<Project>` tags, add the following elements:</span></span>

```xml
<ItemGroup>
<ProjectReference Include="..\PluginBase\PluginBase.csproj">
    <Private>false</Private>
</ProjectReference>
</ItemGroup>
```

<span data-ttu-id="c03ce-156">L'elemento `<Private>false</Private>` è importante.</span><span class="sxs-lookup"><span data-stu-id="c03ce-156">The `<Private>false</Private>` element is important.</span></span> <span data-ttu-id="c03ce-157">Indica a MSBuild di non copiare *PluginBase.dll* nella directory di output per HelloPlugin.</span><span class="sxs-lookup"><span data-stu-id="c03ce-157">This tells MSBuild to not copy *PluginBase.dll* to the output directory for HelloPlugin.</span></span> <span data-ttu-id="c03ce-158">Se l'assembly *PluginBase.dll* è presente nella directory di output, `PluginLoadContext` individuerà l'assembly e lo caricherà durante il caricamento dell'assembly *HelloPlugin.dll*.</span><span class="sxs-lookup"><span data-stu-id="c03ce-158">If the *PluginBase.dll* assembly is present in the output directory, `PluginLoadContext` will find the assembly there and load it when it loads the *HelloPlugin.dll* assembly.</span></span> <span data-ttu-id="c03ce-159">A questo punto, il tipo `HelloPlugin.HelloCommand` implementerà l'interfaccia `ICommand` di *PluginBase.dll* nella directory di output del progetto `HelloPlugin`, non l'interfaccia `ICommand` caricata nel contesto di caricamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="c03ce-159">At this point, the `HelloPlugin.HelloCommand` type will implement the `ICommand` interface from the *PluginBase.dll* in the output directory of the `HelloPlugin` project, not the `ICommand` interface that is loaded into the default load context.</span></span> <span data-ttu-id="c03ce-160">Poiché il runtime Visualizza questi due tipi come tipi diversi da assembly diversi, il metodo `AppWithPlugin.Program.CreateCommands` non troverà i comandi.</span><span class="sxs-lookup"><span data-stu-id="c03ce-160">Since the runtime sees these two types as different types from different assemblies, the `AppWithPlugin.Program.CreateCommands` method won't find the commands.</span></span> <span data-ttu-id="c03ce-161">Di conseguenza, saranno necessari i metadati `<Private>false</Private>` per il riferimento all'assembly che contiene le interfacce dei plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-161">As a result, the `<Private>false</Private>` metadata is required for the reference to the assembly containing the plugin interfaces.</span></span>

<span data-ttu-id="c03ce-162">Dopo aver completato il progetto `HelloPlugin`, è necessario aggiornare il progetto `AppWithPlugin` per individuare dove è possibile trovare il plug-in `HelloPlugin`.</span><span class="sxs-lookup"><span data-stu-id="c03ce-162">Now that the `HelloPlugin` project is complete, we should update the `AppWithPlugin` project to know where the `HelloPlugin` plugin can be found.</span></span> <span data-ttu-id="c03ce-163">Dopo il commento `// Paths to plugins to load`, aggiungere `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` come elemento della matrice `pluginPaths`.</span><span class="sxs-lookup"><span data-stu-id="c03ce-163">After the `// Paths to plugins to load` comment, add `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` as an element of the `pluginPaths` array.</span></span>

## <a name="plugin-with-library-dependencies"></a><span data-ttu-id="c03ce-164">Plug-in con dipendenze di libreria</span><span class="sxs-lookup"><span data-stu-id="c03ce-164">Plugin with library dependencies</span></span>

<span data-ttu-id="c03ce-165">Quasi tutti i plug-in sono più complessi rispetto a un semplice "Hello World" e molti plug-in hanno dipendenze in altre librerie.</span><span class="sxs-lookup"><span data-stu-id="c03ce-165">Almost all plugins are more complex than a simple "Hello World", and many plugins have dependencies on other libraries.</span></span> <span data-ttu-id="c03ce-166">I progetti di plug-in `JsonPlugin` e `OldJson` mostrano due esempi di plug-in con dipendenze del pacchetto NuGet in `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="c03ce-166">The `JsonPlugin` and `OldJson` plugin projects in the sample show two examples of plugins with NuGet package dependencies on `Newtonsoft.Json`.</span></span> <span data-ttu-id="c03ce-167">I file di progetto non dispongono di informazioni speciali per i riferimenti al progetto e (dopo aver aggiunto i percorsi del plug-in all'array `pluginPaths`) i plug-in vengono eseguiti perfettamente, anche se vengono eseguiti nella stessa esecuzione dell'app AppWithPlugin.</span><span class="sxs-lookup"><span data-stu-id="c03ce-167">The project files themselves don't have any special information for the project references, and (after adding the plugin paths to the `pluginPaths` array) the plugins run perfectly, even if run in the same execution of the AppWithPlugin app.</span></span> <span data-ttu-id="c03ce-168">Tuttavia, questi progetti non copiano gli assembly a cui si fa riferimento nella directory di output, quindi gli assembly devono essere presenti nel computer dell'utente per consentire il funzionamento dei plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-168">However, these projects don't copy the referenced assemblies to their output directory, so the assemblies need to be present on the user's machine for the plugins to work.</span></span> <span data-ttu-id="c03ce-169">Questo problema può essere risolto in due modi.</span><span class="sxs-lookup"><span data-stu-id="c03ce-169">There are two ways to work around this problem.</span></span> <span data-ttu-id="c03ce-170">La prima opzione consiste nell'usare il comando `dotnet publish` per pubblicare la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="c03ce-170">The first option is to use the `dotnet publish` command to publish the class library.</span></span> <span data-ttu-id="c03ce-171">In alternativa, se si vuole essere in grado di usare l'output di `dotnet build` per il plug-in, è possibile aggiungere la proprietà `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` tra i due tag `<PropertyGroup>` nel file di progetto del plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-171">Alternatively, if you want to be able to use the output of `dotnet build` for your plugin, you can add the `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` property between the `<PropertyGroup>` tags in the plugin's project file.</span></span> <span data-ttu-id="c03ce-172">Vedere il progetto di plug-in `XcopyablePlugin` per un esempio.</span><span class="sxs-lookup"><span data-stu-id="c03ce-172">See the `XcopyablePlugin` plugin project for an example.</span></span>

## <a name="other-examples-in-the-sample"></a><span data-ttu-id="c03ce-173">Altri esempi nell'esempio</span><span class="sxs-lookup"><span data-stu-id="c03ce-173">Other examples in the sample</span></span>

<span data-ttu-id="c03ce-174">Il codice sorgente completo per questa esercitazione è reperibile nel [repository dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span><span class="sxs-lookup"><span data-stu-id="c03ce-174">The complete source code for this tutorial can be found in [the dotnet/samples repository](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span> <span data-ttu-id="c03ce-175">L'esempio completato include alcuni altri esempi del comportamento di `AssemblyDependencyResolver`.</span><span class="sxs-lookup"><span data-stu-id="c03ce-175">The completed sample includes a few other examples of `AssemblyDependencyResolver` behavior.</span></span> <span data-ttu-id="c03ce-176">Ad esempio, l'oggetto `AssemblyDependencyResolver` può anche risolvere le librerie native nonché gli assembly satellite localizzati inclusi nei pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="c03ce-176">For example, the `AssemblyDependencyResolver` object can also resolve native libraries as well as localized satellite assemblies included in NuGet packages.</span></span> <span data-ttu-id="c03ce-177">`UVPlugin` e `FrenchPlugin` nel repository degli esempi illustrano questi scenari.</span><span class="sxs-lookup"><span data-stu-id="c03ce-177">The `UVPlugin` and `FrenchPlugin` in the samples repository demonstrate these scenarios.</span></span>

## <a name="reference-a-plugin-from-a-nuget-package"></a><span data-ttu-id="c03ce-178">Fare riferimento a un plug-in da un pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="c03ce-178">Reference a plugin from a NuGet package</span></span>

<span data-ttu-id="c03ce-179">Si supponga che sia presente un'app A con un'interfaccia di plug-in definita nel pacchetto NuGet denominato `A.PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="c03ce-179">Let's say that there is an app A that has a plugin interface defined in the NuGet package named `A.PluginBase`.</span></span> <span data-ttu-id="c03ce-180">Come fare riferimento correttamente al pacchetto nel progetto di plug-in?</span><span class="sxs-lookup"><span data-stu-id="c03ce-180">How do you reference the package correctly in your plugin project?</span></span> <span data-ttu-id="c03ce-181">Per i riferimenti al progetto, l'uso dei metadati `<Private>false</Private>` nell'elemento `ProjectReference` nel file di progetto ha impedito la copia della dll nell'output.</span><span class="sxs-lookup"><span data-stu-id="c03ce-181">For project references, using the `<Private>false</Private>` metadata on the `ProjectReference` element in the project file prevented the dll from being copied to the output.</span></span>

<span data-ttu-id="c03ce-182">Per fare riferimento correttamente al pacchetto `A.PluginBase`, si modifica l'elemento `<PackageReference>` nel file di progetto come segue:</span><span class="sxs-lookup"><span data-stu-id="c03ce-182">To correctly reference the `A.PluginBase` package, you want to change the `<PackageReference>` element in the project file to the following:</span></span>

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

<span data-ttu-id="c03ce-183">In questo modo si impedisce che gli assembly `A.PluginBase` vengano copiati nella directory di output del plug-in e si garantisce che il plug-in usi la versione A di `A.PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="c03ce-183">This prevents the `A.PluginBase` assemblies from being copied to the output directory of your plugin and ensures that your plugin will use A's version of `A.PluginBase`.</span></span>

## <a name="plugin-target-framework-recommendations"></a><span data-ttu-id="c03ce-184">Consigli sul framework di destinazione del plug-in</span><span class="sxs-lookup"><span data-stu-id="c03ce-184">Plugin target framework recommendations</span></span>

<span data-ttu-id="c03ce-185">Poiché il caricamento delle dipendenze del plug-in usa il file *deps.json*, tenere presente la raccomandazione relativa al framework di destinazione del plug-in.</span><span class="sxs-lookup"><span data-stu-id="c03ce-185">Because plugin dependency loading uses the *.deps.json* file, there is a gotcha related to the plugin's target framework.</span></span> <span data-ttu-id="c03ce-186">In particolare, è consigliabile che i plug-in abbiano come destinazione un runtime, ad esempio .NET Core 3.0, anziché una versione di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c03ce-186">Specifically, your plugins should target a runtime, such as .NET Core 3.0, instead of a version of .NET Standard.</span></span> <span data-ttu-id="c03ce-187">Il file *.deps.json* viene generato in base al framework di destinazione del progetto e poiché numerosi pacchetti compatibili con .NET Standard offrono assembly di riferimento per la compilazione in .NET Standard e assembly di implementazione per runtime specifici, è possibile che *.deps.json* non consideri correttamente gli assembly di implementazione oppure ottenga la versione .NET Standard di un assembly anziché la versione .NET Core prevista.</span><span class="sxs-lookup"><span data-stu-id="c03ce-187">The *.deps.json* file is generated based on which framework the project targets, and since many .NET Standard-compatible packages ship reference assemblies for building against .NET Standard and implementation assemblies for specific runtimes, the *.deps.json* may not correctly see implementation assemblies, or it may grab the .NET Standard version of an assembly instead of the .NET Core version you expect.</span></span>
