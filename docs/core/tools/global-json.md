---
title: panoramica di global.json
description: Informazioni su come usare il file global.json per impostare la versione di .NET Core SDK durante l'esecuzione dei comandi dell'interfaccia della riga di comando di .NET Core.
ms.date: 01/14/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 70257566e1ff30f5c97212a5e0e3c308c27738b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625995"
---
# <a name="globaljson-overview"></a><span data-ttu-id="4faf6-103">panoramica di global.json</span><span class="sxs-lookup"><span data-stu-id="4faf6-103">global.json overview</span></span>

<span data-ttu-id="4faf6-104">**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="4faf6-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="4faf6-105">Il file *global.json* consente di definire la versione di .NET Core SDK usata quando si eseguono comandi dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4faf6-105">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="4faf6-106">La selezione di .NET Core SDK è indipendente dalla specifica del runtime delle destinazioni del progetto.</span><span class="sxs-lookup"><span data-stu-id="4faf6-106">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="4faf6-107">La versione di .NET Core SDK indica quali versioni dell'interfaccia della riga di comando di .NET Core viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="4faf6-107">The .NET Core SDK version indicates which versions of the .NET Core CLI is used.</span></span>

<span data-ttu-id="4faf6-108">In generale, si desidera utilizzare la versione più recente degli strumenti SDK, pertanto non è necessario alcun file *global.json.*</span><span class="sxs-lookup"><span data-stu-id="4faf6-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="4faf6-109">In alcuni scenari avanzati, è possibile controllare la versione degli strumenti SDK e in questo articolo viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="4faf6-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="4faf6-110">Per altre informazioni su come specificare il runtime, vedere [Framework di destinazione](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4faf6-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="4faf6-111">.NET Core SDK cerca un file *global.json* nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.</span><span class="sxs-lookup"><span data-stu-id="4faf6-111">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="4faf6-112">schema global.json</span><span class="sxs-lookup"><span data-stu-id="4faf6-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="4faf6-113">SDK</span><span class="sxs-lookup"><span data-stu-id="4faf6-113">sdk</span></span>

<span data-ttu-id="4faf6-114">Digitare: `object`</span><span class="sxs-lookup"><span data-stu-id="4faf6-114">Type: `object`</span></span>

<span data-ttu-id="4faf6-115">Specifica le informazioni sul .NET Core SDK da selezionare.</span><span class="sxs-lookup"><span data-stu-id="4faf6-115">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="4faf6-116">version</span><span class="sxs-lookup"><span data-stu-id="4faf6-116">version</span></span>

- <span data-ttu-id="4faf6-117">Digitare: `string`</span><span class="sxs-lookup"><span data-stu-id="4faf6-117">Type: `string`</span></span>

- <span data-ttu-id="4faf6-118">Disponibile da: .NET Core 1.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4faf6-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="4faf6-119">La versione del .NET Core SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="4faf6-119">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="4faf6-120">Questo campo:</span><span class="sxs-lookup"><span data-stu-id="4faf6-120">This field:</span></span>

- <span data-ttu-id="4faf6-121">Non dispone del supporto per i caratteri jolly, ovvero è necessario specificare il numero di versione completo.</span><span class="sxs-lookup"><span data-stu-id="4faf6-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="4faf6-122">Non supporta gli intervalli di versione.</span><span class="sxs-lookup"><span data-stu-id="4faf6-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="4faf6-123">allowPrerelease</span><span class="sxs-lookup"><span data-stu-id="4faf6-123">allowPrerelease</span></span>

- <span data-ttu-id="4faf6-124">Digitare: `boolean`</span><span class="sxs-lookup"><span data-stu-id="4faf6-124">Type: `boolean`</span></span>

- <span data-ttu-id="4faf6-125">Disponibile da: .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4faf6-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="4faf6-126">Indica se il sistema di risoluzione SDK deve considerare le versioni non definitive quando si seleziona la versione dell'SDK da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4faf6-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="4faf6-127">Se non si imposta questo valore in modo esplicito, il valore predefinito dipende se si esegue da Visual Studio:If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="4faf6-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="4faf6-128">Se **non** si è in Visual Studio, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="4faf6-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="4faf6-129">Se ci si trova in Visual Studio, viene utilizzato lo stato di versione non definitiva richiesto.</span><span class="sxs-lookup"><span data-stu-id="4faf6-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="4faf6-130">Ovvero, se si utilizza una versione di anteprima di Visual Studio o si imposta l'opzione **Usa anteprime di .NET Core SDK** (in **Strumenti** > **Opzioni opzioni** > **dell'ambiente** > Preview**Features**), il valore predefinito è `true`; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="4faf6-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="4faf6-131">rollForward</span><span class="sxs-lookup"><span data-stu-id="4faf6-131">rollForward</span></span>

- <span data-ttu-id="4faf6-132">Digitare: `string`</span><span class="sxs-lookup"><span data-stu-id="4faf6-132">Type: `string`</span></span>

- <span data-ttu-id="4faf6-133">Disponibile da: .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="4faf6-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="4faf6-134">Criteri di rollforward da utilizzare quando si seleziona una versione SDK, come fallback quando manca una versione specifica dell'SDK o come direttiva per l'utilizzo di una versione superiore.</span><span class="sxs-lookup"><span data-stu-id="4faf6-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="4faf6-135">Una [versione](#version) deve essere `rollForward` specificata con un valore, `latestMajor`a meno che non venga impostato su .</span><span class="sxs-lookup"><span data-stu-id="4faf6-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>

<span data-ttu-id="4faf6-136">Per comprendere i criteri disponibili e il relativo comportamento, `x.y.znn`considerare le seguenti definizioni per una versione SDK nel formato:</span><span class="sxs-lookup"><span data-stu-id="4faf6-136">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="4faf6-137">`x`è la versione principale.</span><span class="sxs-lookup"><span data-stu-id="4faf6-137">`x` is the major version.</span></span>
- <span data-ttu-id="4faf6-138">`y`è la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="4faf6-138">`y` is the minor version.</span></span>
- <span data-ttu-id="4faf6-139">`z`è la banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4faf6-139">`z` is the feature band.</span></span>
- <span data-ttu-id="4faf6-140">`nn`è la versione della patch.</span><span class="sxs-lookup"><span data-stu-id="4faf6-140">`nn` is the patch version.</span></span>

<span data-ttu-id="4faf6-141">Nella tabella seguente vengono illustrati `rollForward` i valori possibili per la chiave:</span><span class="sxs-lookup"><span data-stu-id="4faf6-141">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="4faf6-142">valore</span><span class="sxs-lookup"><span data-stu-id="4faf6-142">Value</span></span>         | <span data-ttu-id="4faf6-143">Comportamento</span><span class="sxs-lookup"><span data-stu-id="4faf6-143">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="4faf6-144">Utilizza la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="4faf6-144">Uses the specified version.</span></span> <br> <span data-ttu-id="4faf6-145">Se non viene trovato, passa all'ultimo livello di patch.</span><span class="sxs-lookup"><span data-stu-id="4faf6-145">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="4faf6-146">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4faf6-146">If not found, fails.</span></span> <br><br> <span data-ttu-id="4faf6-147">Questo valore è il comportamento legacy delle versioni precedenti dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="4faf6-147">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="4faf6-148">Utilizza il livello di patch più recente per la banda principale, secondaria e caratteristica specificata.</span><span class="sxs-lookup"><span data-stu-id="4faf6-148">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="4faf6-149">Se non viene trovato, passa alla banda di funzionalità superiore successiva all'interno dello stesso major/minore e utilizza il livello di patch più recente per tale feature band.</span><span class="sxs-lookup"><span data-stu-id="4faf6-149">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="4faf6-150">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4faf6-150">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="4faf6-151">Utilizza il livello di patch più recente per la banda principale, secondaria e caratteristica specificata.</span><span class="sxs-lookup"><span data-stu-id="4faf6-151">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="4faf6-152">Se non viene trovato, passa alla banda di funzionalità superiore successiva all'interno della stessa versione principale/secondaria e utilizza il livello di patch più recente per tale feature band.</span><span class="sxs-lookup"><span data-stu-id="4faf6-152">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="4faf6-153">Se non viene trovato, passa alla banda secondaria secondaria minore e caratteristica all'interno della stessa major e utilizza il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4faf6-153">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="4faf6-154">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4faf6-154">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="4faf6-155">Utilizza il livello di patch più recente per la banda principale, secondaria e caratteristica specificata.</span><span class="sxs-lookup"><span data-stu-id="4faf6-155">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="4faf6-156">Se non viene trovato, passa alla banda di funzionalità superiore successiva all'interno della stessa versione principale/secondaria e utilizza il livello di patch più recente per tale feature band.</span><span class="sxs-lookup"><span data-stu-id="4faf6-156">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="4faf6-157">Se non viene trovato, passa alla banda secondaria secondaria minore e caratteristica all'interno della stessa major e utilizza il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4faf6-157">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="4faf6-158">Se non viene trovato, passa alla banda maggiore, secondaria e caratteristica superiore successiva e utilizza il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4faf6-158">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="4faf6-159">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4faf6-159">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="4faf6-160">Utilizza l'ultimo livello di patch installato che corrisponde alla banda principale, secondaria e di funzionalità richiesta con un livello di patch maggiore o uguale al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="4faf6-160">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="4faf6-161">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4faf6-161">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="4faf6-162">Utilizza la banda di funzionalità e il livello di patch più elevati installati che corrispondono a quelli richiesti maggiore e minore con una banda di funzionalità maggiore o uguale al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="4faf6-162">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="4faf6-163">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4faf6-163">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="4faf6-164">Utilizza il livello secondario, banda di funzionalità e livello di patch più alto installato che corrisponde al livello principale richiesto con un minore secondario maggiore o uguale al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="4faf6-164">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="4faf6-165">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4faf6-165">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="4faf6-166">Utilizza il più alto .NET Core SDK installato con un'area principale maggiore maggiore o uguale al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="4faf6-166">Uses the highest installed .NET Core SDK with a major that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="4faf6-167">Se non viene trovato, fallire.</span><span class="sxs-lookup"><span data-stu-id="4faf6-167">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="4faf6-168">Non va avanti.</span><span class="sxs-lookup"><span data-stu-id="4faf6-168">Doesn't roll forward.</span></span> <span data-ttu-id="4faf6-169">Corrispondenza esatta richiesta.</span><span class="sxs-lookup"><span data-stu-id="4faf6-169">Exact match required.</span></span> |

## <a name="examples"></a><span data-ttu-id="4faf6-170">Esempi</span><span class="sxs-lookup"><span data-stu-id="4faf6-170">Examples</span></span>

<span data-ttu-id="4faf6-171">L'esempio seguente mostra come non usare le versioni non definitive:The following example shows how to not use prerelease versions:</span><span class="sxs-lookup"><span data-stu-id="4faf6-171">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="4faf6-172">Nell'esempio seguente viene illustrato come utilizzare la versione più recente installata che è maggiore o uguale alla versione specificata:</span><span class="sxs-lookup"><span data-stu-id="4faf6-172">The following example shows how to use the highest version installed that is greater or equal than the specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="4faf6-173">L'esempio seguente mostra come utilizzare l'esatta versione specificata:</span><span class="sxs-lookup"><span data-stu-id="4faf6-173">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="4faf6-174">Nell'esempio seguente viene illustrato come utilizzare la versione di patch più elevata installata di una versione specifica (nel formato 3.1.1xx):</span><span class="sxs-lookup"><span data-stu-id="4faf6-174">The following example shows how to use the highest patch version installed of a specific version (in the form, 3.1.1xx):</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="4faf6-175">global.json e interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="4faf6-175">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="4faf6-176">È utile sapere quali versioni dell'SDK sono installate nel computer per impostarne una nel file *global.json.*</span><span class="sxs-lookup"><span data-stu-id="4faf6-176">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="4faf6-177">Per ulteriori informazioni su come eseguire questa operazione, vedere [come verificare che .NET Core sia già installato](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span><span class="sxs-lookup"><span data-stu-id="4faf6-177">For more information on how to do that, see [How to check that .NET Core is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="4faf6-178">Per installare altre versioni di .NET Core SDK nel computer, visitare la pagina [Scarica .NET Core.](https://dotnet.microsoft.com/download/dotnet-core)</span><span class="sxs-lookup"><span data-stu-id="4faf6-178">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="4faf6-179">È possibile creare un nuovo file *global.json* nella directory corrente eseguendo il comando [dotnet new](dotnet-new.md), in modo simile al seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="4faf6-179">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="4faf6-180">Regole di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="4faf6-180">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="4faf6-181">Le regole di corrispondenza `dotnet.exe` sono regolate dal punto di ingresso, comune a tutti i runtime installati di .NET Core installati.</span><span class="sxs-lookup"><span data-stu-id="4faf6-181">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET Core installed runtimes.</span></span> <span data-ttu-id="4faf6-182">Le regole di corrispondenza per l'ultima versione installata di .NET Core Runtime vengono utilizzate quando si dispone di più runtime installati side-by-side.</span><span class="sxs-lookup"><span data-stu-id="4faf6-182">The matching rules for the latest installed version of the .NET Core Runtime are used when you have multiple runtimes installed side-by-side.</span></span>

## <a name="net-core-3x"></a>[<span data-ttu-id="4faf6-183">.NET Core 3.x</span><span class="sxs-lookup"><span data-stu-id="4faf6-183">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="4faf6-184">A partire da .NET Core 3.0, si applicano le regole seguenti per determinare la versione dell'SDK da utilizzare:</span><span class="sxs-lookup"><span data-stu-id="4faf6-184">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="4faf6-185">Se non viene trovato alcun file *global.json* o *global.json* `allowPrerelease` non specifica una versione SDK né un `rollForward` `latestMajor`valore, viene utilizzata la versione SDK installata più la più alta (equivalente all'impostazione su ).</span><span class="sxs-lookup"><span data-stu-id="4faf6-185">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="4faf6-186">La versione precedente dell'SDK `dotnet` viene considerata dipende da come viene richiamata.</span><span class="sxs-lookup"><span data-stu-id="4faf6-186">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="4faf6-187">Se **non** si è in Visual Studio, vengono considerate le versioni non definitive.</span><span class="sxs-lookup"><span data-stu-id="4faf6-187">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="4faf6-188">Se ci si trova in Visual Studio, viene utilizzato lo stato di versione non definitiva richiesto.</span><span class="sxs-lookup"><span data-stu-id="4faf6-188">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="4faf6-189">Ovvero, se si utilizza una versione di anteprima di Visual Studio o si imposta l'opzione **Usa anteprime di .NET Core SDK** (in **Strumenti** > **Opzioni** > opzioni**dell'ambiente\*\*\*\*Environment** > Preview Features ), vengono considerate le versioni di non definitive; in caso contrario, vengono considerate solo le versioni di rilascio.</span><span class="sxs-lookup"><span data-stu-id="4faf6-189">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="4faf6-190">Se viene trovato un file *global.json* che non specifica una `allowPrerelease` versione SDK ma specifica un valore, `rollForward` `latestMajor`viene utilizzata la versione SDK installata più alta (equivalente all'impostazione su ).</span><span class="sxs-lookup"><span data-stu-id="4faf6-190">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="4faf6-191">Il fatto che la versione più recente dell'SDK possa essere release o non definitiva dipende dal valore di `allowPrerelease`.</span><span class="sxs-lookup"><span data-stu-id="4faf6-191">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="4faf6-192">`true`indica che vengono considerate le versioni non definitive; `false` indica che vengono considerate solo le versioni di rilascio.</span><span class="sxs-lookup"><span data-stu-id="4faf6-192">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="4faf6-193">Se viene trovato un file *global.json* che specifica una versione SDK:</span><span class="sxs-lookup"><span data-stu-id="4faf6-193">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="4faf6-194">Se `rollFoward` non è impostato `latestPatch` alcun valore, viene utilizzato come criterio predefinito. `rollForward`</span><span class="sxs-lookup"><span data-stu-id="4faf6-194">If no `rollFoward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="4faf6-195">In caso contrario, controllare ogni valore e il relativo comportamento nella sezione [rollForward.](#rollforward)</span><span class="sxs-lookup"><span data-stu-id="4faf6-195">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="4faf6-196">Se le versioni non definitive vengono considerate `allowPrerelease` e qual è il comportamento predefinito quando non è impostato è descritto nella sezione [allowPrerelease.](#allowprerelease)</span><span class="sxs-lookup"><span data-stu-id="4faf6-196">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2x"></a>[<span data-ttu-id="4faf6-197">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4faf6-197">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="4faf6-198">In .NET Core 2.x SDK, le regole seguenti si applicano quando si determina la versione dell'SDK da utilizzare:</span><span class="sxs-lookup"><span data-stu-id="4faf6-198">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="4faf6-199">Se non vengono trovati file *global.json* o *global.json* non specifica una versione SDK, viene usata l'ultima versione SDK installata.</span><span class="sxs-lookup"><span data-stu-id="4faf6-199">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="4faf6-200">La versione più recente dell'SDK può essere la versione non definitiva o la versione non definitiva: vince il numero di versione più alto.</span><span class="sxs-lookup"><span data-stu-id="4faf6-200">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="4faf6-201">Se *global.json* specifica una versione SDK:</span><span class="sxs-lookup"><span data-stu-id="4faf6-201">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="4faf6-202">Se la versione SDK indicata è presente nel computer, si usa quella versione.</span><span class="sxs-lookup"><span data-stu-id="4faf6-202">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="4faf6-203">Se la versione SDK specificata non è presente nel computer, viene usata la **versione patch** SDK installata più recente.</span><span class="sxs-lookup"><span data-stu-id="4faf6-203">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="4faf6-204">L'ultima versione della **patch** SDK installata può essere la versione finale o la versione non definitiva: vince il numero di versione più alto.</span><span class="sxs-lookup"><span data-stu-id="4faf6-204">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="4faf6-205">In .NET Core 2.1 e versioni successive, le **versioni patch** inferiori alla **versione patch** specificata vengono ignorate nella selezione del SDK.</span><span class="sxs-lookup"><span data-stu-id="4faf6-205">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="4faf6-206">Se non è possibile trovare la versione SDK specificata e una **versione patch** SDK appropriata, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="4faf6-206">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="4faf6-207">La versione SDK è composta dalle seguenti parti:</span><span class="sxs-lookup"><span data-stu-id="4faf6-207">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="4faf6-208">La **versione definitiva** di .NET Core SDK è rappresentata dalla prima cifra (`x`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive.</span><span class="sxs-lookup"><span data-stu-id="4faf6-208">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="4faf6-209">In generale, .NET Core SDK ha un ciclo di rilascio più veloce rispetto a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4faf6-209">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="4faf6-210">La **versione patch** è definita dalle ultime due cifre (`yz`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive.</span><span class="sxs-lookup"><span data-stu-id="4faf6-210">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="4faf6-211">Ad esempio, se si specifica `2.1.300` come versione SDK, la selezione del SDK può arrivare fino a `2.1.399` ma `2.1.400` non è considerata una versione patch per `2.1.300`.</span><span class="sxs-lookup"><span data-stu-id="4faf6-211">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="4faf6-212">Le versioni di .NET core SDK da `2.1.100` a `2.1.201` sono state rilasciate durante la transizione tra gli schemi dei numeri di versione e non gestiscono correttamente la notazione `xyz`.</span><span class="sxs-lookup"><span data-stu-id="4faf6-212">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="4faf6-213">Se queste versioni vengono specificate nel file *global.json*, è consigliabile verificare che tali versioni siano presenti nei computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4faf6-213">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshoot-build-warnings"></a><span data-ttu-id="4faf6-214">Risolvere i problemi relativi agli avvisi di compilazioneTroubleshoot build</span><span class="sxs-lookup"><span data-stu-id="4faf6-214">Troubleshoot build warnings</span></span>

* <span data-ttu-id="4faf6-215">L'avviso seguente indica che il progetto è stato compilato utilizzando una versione non definitiva di .NET Core SDK:</span><span class="sxs-lookup"><span data-stu-id="4faf6-215">The following warning indicates that your project was compiled using a prerelease version of the .NET Core SDK:</span></span>

  > <span data-ttu-id="4faf6-216">Si sta lavorando con una versione di anteprima di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="4faf6-216">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="4faf6-217">È possibile definire la versione SDK tramite un file global.json nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="4faf6-217">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="4faf6-218">Per <https://go.microsoft.com/fwlink/?linkid=869452>saperne di più su .</span><span class="sxs-lookup"><span data-stu-id="4faf6-218">More at <https://go.microsoft.com/fwlink/?linkid=869452>.</span></span>

  <span data-ttu-id="4faf6-219">Le versioni di .NET Core SDK hanno una storia e un impegno di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="4faf6-219">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="4faf6-220">Tuttavia, se non si vuole usare una versione non definitiva, controllare le diverse strategie che è possibile usare con .NET Core 3.0 SDK o versione successiva nella sezione [allowPrerelease.](#allowprerelease)</span><span class="sxs-lookup"><span data-stu-id="4faf6-220">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="4faf6-221">Per i computer in cui non è mai stato installato un runtime o SDK .NET Core 3.0 o versione successiva, è necessario creare un file *global.json* e specificare la versione esatta che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4faf6-221">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

* <span data-ttu-id="4faf6-222">L'avviso seguente indica che il progetto è destinato a EF Core 1.0 o 1.1, che non è compatibile con .NET Core 2.1 SDK e versioni successive:</span><span class="sxs-lookup"><span data-stu-id="4faf6-222">The following warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions:</span></span>

  > <span data-ttu-id="4faf6-223">Progetto di avvio '{startupProject}' framework di destinazione '.NETCoreApp' versione '{targetFrameworkVersion}'.</span><span class="sxs-lookup"><span data-stu-id="4faf6-223">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="4faf6-224">Questa versione degli strumenti della riga di comando di Entity Framework Core .NET supporta solo la versione 2.0 o successive.</span><span class="sxs-lookup"><span data-stu-id="4faf6-224">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="4faf6-225">Per informazioni sull'utilizzo di versioni <https://go.microsoft.com/fwlink/?linkid=871254>precedenti degli strumenti, vedere .</span><span class="sxs-lookup"><span data-stu-id="4faf6-225">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254>.</span></span>

  <span data-ttu-id="4faf6-226">A partire da .NET Core 2.1 SDK (versione 2.1.300), il comando `dotnet ef` è incluso nell'SDK.</span><span class="sxs-lookup"><span data-stu-id="4faf6-226">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="4faf6-227">Per compilare il progetto, installare .NET Core 2.0 SDK (versione 2.1.201) o precedente nel computer e definire la versione SDK desiderata utilizzando il file *global.json.*</span><span class="sxs-lookup"><span data-stu-id="4faf6-227">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) or earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="4faf6-228">Per altre informazioni sul comando `dotnet ef`, vedere [Strumenti da riga di comando di EF Core .NET](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="4faf6-228">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="4faf6-229">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4faf6-229">See also</span></span>

- [<span data-ttu-id="4faf6-230">Come vengono risolti gli SDK di progetto</span><span class="sxs-lookup"><span data-stu-id="4faf6-230">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
