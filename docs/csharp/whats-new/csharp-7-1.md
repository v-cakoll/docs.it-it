---
title: Novità di C# 7.1
description: Panoramica delle nuove funzionalità in C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="71668-103">Novità di C# 7.1</span><span class="sxs-lookup"><span data-stu-id="71668-103">What's new in C# 7.1</span></span>

<span data-ttu-id="71668-104">C# 7.1 è la prima versione intermedia del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="71668-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="71668-105">Indica una maggiore frequenza per il rilascio delle versioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="71668-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="71668-106">Le nuove funzionalità possono essere usate prima, idealmente non appena ognuna di esse è pronta.</span><span class="sxs-lookup"><span data-stu-id="71668-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="71668-107">C# 7.1 aggiunge la possibilità di configurare il compilatore in modo che corrisponda a una specifica versione del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="71668-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="71668-108">Questo consente di separare la decisione di eseguire l'aggiornamento di strumenti dalla decisione di eseguire l'aggiornamento delle versioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="71668-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="71668-109">C# 7.1 aggiunge l'elemento di configurazione per la [selezione della versione del linguaggio](#language-version-selection), tre nuove funzionalità del linguaggio e il nuovo comportamento del compilatore.</span><span class="sxs-lookup"><span data-stu-id="71668-109">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="71668-110">Le nuove funzionalità relative al linguaggio in questa versione sono:</span><span class="sxs-lookup"><span data-stu-id="71668-110">The new language features in this release are:</span></span>

* <span data-ttu-id="71668-111">Metodo [`async` `Main` ](#async-main)</span><span class="sxs-lookup"><span data-stu-id="71668-111">[`async` `Main` method](#async-main)</span></span>
  - <span data-ttu-id="71668-112">Il punto di ingresso per un'applicazione può avere il modificatore `async`.</span><span class="sxs-lookup"><span data-stu-id="71668-112">The entry point for an application can have the `async` modifier.</span></span>
* <span data-ttu-id="71668-113">Espressioni letterali [`default` ](#default-literal-expressions)</span><span class="sxs-lookup"><span data-stu-id="71668-113">[`default` literal expressions](#default-literal-expressions)</span></span>
  - <span data-ttu-id="71668-114">Quando è possibile dedurre il tipo di destinazione, si possono usare espressioni letterali predefinite nelle espressioni con valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="71668-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="71668-115">Nomi di elemento di tupla dedotti</span><span class="sxs-lookup"><span data-stu-id="71668-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="71668-116">In molti casi i nomi degli elementi della tupla possono essere dedotti dall'inizializzazione tupla.</span><span class="sxs-lookup"><span data-stu-id="71668-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="71668-117">Infine, il compilatore offre due opzioni `/refout` e `/refonly` che controllano la [generazione dell'assembly di riferimento](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="71668-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="71668-118">Selezione della versione del linguaggio</span><span class="sxs-lookup"><span data-stu-id="71668-118">Language version selection</span></span>

<span data-ttu-id="71668-119">Il compilatore C# supporta C# 7.1 a partire da Visual Studio 2017 versione 15.3 o .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="71668-119">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="71668-120">Le funzionalità della versione 7.1 sono tuttavia disattivate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="71668-120">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="71668-121">Per abilitare le funzionalità della versione 7.1, è necessario modificare l'impostazione della versione del linguaggio per il progetto.</span><span class="sxs-lookup"><span data-stu-id="71668-121">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="71668-122">In Visual Studio fare clic con il pulsante destro del mouse sul nodo del progetto in Esplora soluzioni e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="71668-122">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="71668-123">Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="71668-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="71668-124">Nell'elenco a discesa selezionare l'**Ultima versione secondaria di C# (più recente)** o la versione specifica **C# 7.1** come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="71668-124">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="71668-125">Il valore `latest` indica che si intende usare l'ultima versione secondaria nel computer corrente.</span><span class="sxs-lookup"><span data-stu-id="71668-125">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="71668-126">Il valore `C# 7.1` indica che si intende usare C# 7.1 anche dopo il rilascio di versioni secondarie successive.</span><span class="sxs-lookup"><span data-stu-id="71668-126">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![Impostazione della versione del linguaggio](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="71668-128">In alternativa, è possibile modificare il file "csproj" e aggiungere o modificare le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="71668-128">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="71668-129">Se si usa l'IDE di Visual Studio per aggiornare i file csproj, l'IDE crea nodi separati per ogni configurazione della build.</span><span class="sxs-lookup"><span data-stu-id="71668-129">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="71668-130">In genere si imposta lo stesso valore in tutte le configurazioni della build, ma è necessario impostarlo in modo esplicito per ogni configurazione della build o selezionare "Tutte le configurazioni" quando si modifica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="71668-130">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="71668-131">Nel file csproj verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="71668-131">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="71668-132">Le impostazioni valide per l'elemento `LangVersion` sono:</span><span class="sxs-lookup"><span data-stu-id="71668-132">Valid settings for the `LangVersion` element are:</span></span>

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

<span data-ttu-id="71668-133">Le stringhe speciali `default` e `latest` si risolvono rispettivamente nelle versioni principale e secondaria più recenti del linguaggio installate nel computer di compilazione.</span><span class="sxs-lookup"><span data-stu-id="71668-133">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="71668-134">Questa impostazione separa l'installazione delle nuove versioni di SDK e strumenti nell'ambiente di sviluppo dalla scelta di incorporare nuove funzionalità del linguaggio in un progetto.</span><span class="sxs-lookup"><span data-stu-id="71668-134">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="71668-135">È possibile installare l'SDK e gli strumenti più recenti nel computer di compilazione.</span><span class="sxs-lookup"><span data-stu-id="71668-135">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="71668-136">Ogni progetto può essere configurato per usare una versione specifica del linguaggio in base alla relativa build.</span><span class="sxs-lookup"><span data-stu-id="71668-136">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="71668-137">Async main</span><span class="sxs-lookup"><span data-stu-id="71668-137">Async main</span></span>

<span data-ttu-id="71668-138">Un metodo *async main* consente di usare `await` nel proprio metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="71668-138">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="71668-139">In precedenza sarebbe stato necessario scrivere:</span><span class="sxs-lookup"><span data-stu-id="71668-139">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="71668-140">Ora è possibile scrivere:</span><span class="sxs-lookup"><span data-stu-id="71668-140">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="71668-141">Se il programma non restituisce un codice di uscita, è possibile dichiarare un metodo `Main` che restituisce una classe <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="71668-141">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="71668-142">Per altre informazioni dettagliate, leggere l'argomento [async main](../programming-guide/main-and-command-args/index.md) nella guida alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="71668-142">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="71668-143">Espressioni letterali predefinite</span><span class="sxs-lookup"><span data-stu-id="71668-143">Default literal expressions</span></span>

<span data-ttu-id="71668-144">Le espressioni letterali predefinite rappresentano un miglioramento delle espressioni con valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="71668-144">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="71668-145">Queste espressioni inizializzano una variabile sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="71668-145">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="71668-146">Mentre in precedenza si sarebbe scritto:</span><span class="sxs-lookup"><span data-stu-id="71668-146">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="71668-147">È ora possibile omettere il tipo sul lato destro dell'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="71668-147">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="71668-148">Altre informazioni su questo miglioramento sono disponibili nell'argomento della Guida per programmatori C# relativo alle [espressioni con valore predefinito](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="71668-148">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="71668-149">Questo miglioramento modifica anche alcune delle regole di analisi per la [parola chiave default](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="71668-149">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="71668-150">Nomi di elemento di tupla dedotti</span><span class="sxs-lookup"><span data-stu-id="71668-150">Inferred tuple element names</span></span>

<span data-ttu-id="71668-151">Questa funzionalità costituisce un piccolo miglioramento alla funzionalità relativa alle tuple introdotta in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="71668-151">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="71668-152">Molte volte, quando si inizializza una tupla, le variabili usate per il lato destro dell'assegnazione corrispondono esattamente ai nomi che si vorrebbero usare per gli elementi della tupla:</span><span class="sxs-lookup"><span data-stu-id="71668-152">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="71668-153">I nomi degli elementi della tupla possono essere dedotti dalle variabili usate per inizializzare la tupla in C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="71668-153">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="71668-154">Informazioni più approfondite sulle tuple sono disponibili nell'argomento [Tuple](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="71668-154">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="71668-155">Generazione assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="71668-155">Reference assembly generation</span></span>

<span data-ttu-id="71668-156">Sono disponibili due nuove opzioni del compilatore che generano *gli assembly di solo riferimento* : [/refout](../language-reference/compiler-options/refout-compiler-option.md) e [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="71668-156">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="71668-157">Gli argomenti collegati illustrano in modo più dettagliato queste opzioni e gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="71668-157">The linked topics explain these options and reference assemblies in more detail.</span></span>
