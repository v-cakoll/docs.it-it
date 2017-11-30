---
title: "Novità di c# 7.1"
description: "Panoramica delle nuove funzionalità in c# 7.1."
keywords: Progettazione del linguaggio c#, 7.1, Visual Studio 2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="a2706-104">Novità di c# 7.1</span><span class="sxs-lookup"><span data-stu-id="a2706-104">What's new in C# 7.1</span></span>

<span data-ttu-id="a2706-105">C# 7.1 è il primo punto di rilascio del linguaggio c#.</span><span class="sxs-lookup"><span data-stu-id="a2706-105">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="a2706-106">Contrassegna un rilasci maggiore per la lingua.</span><span class="sxs-lookup"><span data-stu-id="a2706-106">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="a2706-107">È possibile utilizzare le nuove funzionalità prima, idealmente quando ogni nuova funzionalità è pronta.</span><span class="sxs-lookup"><span data-stu-id="a2706-107">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="a2706-108">7.1 c# aggiunge la possibilità di configurare il compilatore in modo che corrisponda a una versione specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="a2706-108">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="a2706-109">Che consente di separare la decisione di eseguire l'aggiornamento di strumenti della decisione di eseguire l'aggiornamento di versioni in lingue diverse.</span><span class="sxs-lookup"><span data-stu-id="a2706-109">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="a2706-110">7.1 c# aggiunge il [selezione della lingua versione](#language-version-selection) elemento di configurazione, tre nuove funzionalità del linguaggio e il nuovo comportamento del compilatore.</span><span class="sxs-lookup"><span data-stu-id="a2706-110">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="a2706-111">Le nuove funzionalità del linguaggio in questa versione sono:</span><span class="sxs-lookup"><span data-stu-id="a2706-111">The new language features in this release are:</span></span>

* [<span data-ttu-id="a2706-112">`async``Main` (metodo)</span><span class="sxs-lookup"><span data-stu-id="a2706-112">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="a2706-113">Il punto di ingresso per un'applicazione può avere il `async` modificatore.</span><span class="sxs-lookup"><span data-stu-id="a2706-113">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="a2706-114">`default`espressioni letterali</span><span class="sxs-lookup"><span data-stu-id="a2706-114">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="a2706-115">Quando è possibile dedurre il tipo di destinazione, è possibile utilizzare espressioni letterali predefinite nelle espressioni di valori predefinito.</span><span class="sxs-lookup"><span data-stu-id="a2706-115">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="a2706-116">Nomi di elemento dedotto tupla</span><span class="sxs-lookup"><span data-stu-id="a2706-116">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="a2706-117">I nomi degli elementi di tupla possono essere dedotto dall'inizializzazione tupla in molti casi.</span><span class="sxs-lookup"><span data-stu-id="a2706-117">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="a2706-118">Infine, il compilatore è disponibili due opzioni `/refout` e `/refonly` tale controllo [la generazione di assembly di riferimento](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="a2706-118">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="a2706-119">Selezione della lingua della versione</span><span class="sxs-lookup"><span data-stu-id="a2706-119">Language version selection</span></span>

<span data-ttu-id="a2706-120">Il compilatore c# supporta 7.1 c# a partire da Visual Studio 2017 versione 15.3 o .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="a2706-120">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="a2706-121">Tuttavia, le 7.1 funzionalità sono disattivate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a2706-121">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="a2706-122">Per abilitare le 7.1 funzionalità, è necessario modificare l'impostazione della versione di lingua per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a2706-122">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="a2706-123">In Visual Studio, fare clic sul nodo del progetto in Esplora soluzioni e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a2706-123">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="a2706-124">Selezionare il **compilare** e selezionare il **avanzate** pulsante.</span><span class="sxs-lookup"><span data-stu-id="a2706-124">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="a2706-125">Nell'elenco a discesa, selezionare **c# versione secondaria più recente (versione più recente)**, o la versione **c# 7.1** come illustrato nella seguente immagine.</span><span class="sxs-lookup"><span data-stu-id="a2706-125">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="a2706-126">Il `latest` valore indica che si desidera utilizzare la versione secondaria più recente nel computer corrente.</span><span class="sxs-lookup"><span data-stu-id="a2706-126">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="a2706-127">Il `C# 7.1` significa che si desidera utilizzare c# 7.1, anche dopo che vengono rilasciate le versioni secondarie successive.</span><span class="sxs-lookup"><span data-stu-id="a2706-127">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![Impostazione della versione di lingua](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="a2706-129">In alternativa, è possibile modificare il file "csproj" e aggiungere o modificare le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2706-129">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="a2706-130">Se si utilizza l'IDE di Visual Studio di aggiornare i file csproj, l'IDE crea nodi diversi per ogni configurazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a2706-130">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="a2706-131">È in genere imposta il valore lo stesso in tutte le configurazioni di compilazione, ma è necessario impostarlo in modo esplicito per ogni configurazione di compilazione o selezionare "Tutte le configurazioni" quando si modifica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="a2706-131">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="a2706-132">Nel file csproj, verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a2706-132">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a2706-133">Le impostazioni valide per il `LangVersion` elemento sono:</span><span class="sxs-lookup"><span data-stu-id="a2706-133">Valid settings for the `LangVersion` element are:</span></span>

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

<span data-ttu-id="a2706-134">Le stringhe speciali `default` e `latest` risolvere per le versioni in lingua principale e secondaria più recente installate nel computer di compilazione, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="a2706-134">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="a2706-135">Questa impostazione separa l'installazione di nuove versioni del SDK e strumenti nell'ambiente di sviluppo dalla scelta di incorporare nuove funzionalità del linguaggio in un progetto.</span><span class="sxs-lookup"><span data-stu-id="a2706-135">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="a2706-136">È possibile installare il SDK e strumenti più recenti nel computer di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a2706-136">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="a2706-137">Ogni progetto può essere configurato per utilizzare una versione specifica del linguaggio per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="a2706-137">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="a2706-138">Async principale</span><span class="sxs-lookup"><span data-stu-id="a2706-138">Async main</span></span>

<span data-ttu-id="a2706-139">Un *async principale* metodo consente di utilizzare `await` nel `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="a2706-139">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="a2706-140">In precedenza, è necessario scrivere:</span><span class="sxs-lookup"><span data-stu-id="a2706-140">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="a2706-141">Ora è possibile scrivere:</span><span class="sxs-lookup"><span data-stu-id="a2706-141">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="a2706-142">Se il programma non restituisce un codice di uscita, è possibile dichiarare un `Main` metodo che restituisce un <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="a2706-142">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="a2706-143">È possibile leggere informazioni sui dettagli nel [async principale](../programming-guide/main-and-command-args/index.md) argomento nella Guida di programmazione.</span><span class="sxs-lookup"><span data-stu-id="a2706-143">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="a2706-144">Espressioni letterali predefinito</span><span class="sxs-lookup"><span data-stu-id="a2706-144">Default literal expressions</span></span>

<span data-ttu-id="a2706-145">Le espressioni letterali predefinito rappresentano un progresso espressioni di valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a2706-145">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="a2706-146">Queste espressioni di inizializzare una variabile sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a2706-146">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="a2706-147">In cui in precedenza scrivere:</span><span class="sxs-lookup"><span data-stu-id="a2706-147">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="a2706-148">È ora possibile omettere il tipo sul lato destro dell'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="a2706-148">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="a2706-149">Maggiori informazioni su questa funzionalità avanzata nell'argomento della Guida per programmatori c# in [predefinito espressioni valore](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a2706-149">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="a2706-150">Questa funzionalità avanzata modifica anche alcune delle regole di analisi per il [parola chiave default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="a2706-150">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="a2706-151">Nomi di elemento dedotto tupla</span><span class="sxs-lookup"><span data-stu-id="a2706-151">Inferred tuple element names</span></span>

<span data-ttu-id="a2706-152">Questa funzionalità è un piccolo miglioramento alla funzionalità tuple introdotta in c# 7.0.</span><span class="sxs-lookup"><span data-stu-id="a2706-152">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="a2706-153">Molte volte quando l'inizializzazione di una tupla, le variabili utilizzate per il lato destro dell'assegnazione sono gli stessi nomi di cui che si desidera usare gli elementi della tupla:</span><span class="sxs-lookup"><span data-stu-id="a2706-153">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="a2706-154">I nomi degli elementi di tupla possono essere dedotto da variabili utilizzate per inizializzare la tupla in c# 7.1:</span><span class="sxs-lookup"><span data-stu-id="a2706-154">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="a2706-155">Per ulteriori informazioni su questa funzionalità in informazioni di [Tuple](../tuples.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="a2706-155">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="a2706-156">Generazione di assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="a2706-156">Reference assembly generation</span></span>

<span data-ttu-id="a2706-157">Sono disponibili due nuove opzioni del compilatore che generano *gli assembly di riferimento sola*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) e [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a2706-157">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="a2706-158">Gli argomenti collegati illustrano queste opzioni e gli assembly di riferimento in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="a2706-158">The linked topics explain these options and reference assemblies in more detail.</span></span>
