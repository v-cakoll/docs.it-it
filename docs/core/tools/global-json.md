---
title: panoramica di global.json
description: Informazioni su come usare il file global.json per impostare la versione di .NET Core SDK durante l'esecuzione dei comandi dell'interfaccia della riga di comando di .NET Core.
ms.date: 05/01/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 5078bc03056c23bccf02e027441de72c69072c7d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202035"
---
# <a name="globaljson-overview"></a><span data-ttu-id="841a2-103">panoramica di global.json</span><span class="sxs-lookup"><span data-stu-id="841a2-103">global.json overview</span></span>

<span data-ttu-id="841a2-104">**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="841a2-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="841a2-105">Il file *global.json* consente di definire la versione di .NET Core SDK usata quando si eseguono comandi dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="841a2-105">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="841a2-106">La selezione di .NET Core SDK è indipendente dalla specifica del runtime delle destinazioni del progetto.</span><span class="sxs-lookup"><span data-stu-id="841a2-106">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="841a2-107">La versione .NET Core SDK indica le versioni di interfaccia della riga di comando di .NET Core utilizzate.</span><span class="sxs-lookup"><span data-stu-id="841a2-107">The .NET Core SDK version indicates which versions of the .NET Core CLI is used.</span></span>

<span data-ttu-id="841a2-108">In generale, si vuole usare la versione più recente degli strumenti SDK, pertanto non è necessario alcun file *Global. JSON* .</span><span class="sxs-lookup"><span data-stu-id="841a2-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="841a2-109">In alcuni scenari avanzati, potrebbe essere necessario controllare la versione degli strumenti SDK e in questo articolo viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="841a2-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="841a2-110">Per altre informazioni su come specificare il runtime, vedere [Framework di destinazione](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="841a2-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="841a2-111">.NET Core SDK cerca un file *global.json* nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.</span><span class="sxs-lookup"><span data-stu-id="841a2-111">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="841a2-112">schema global.json</span><span class="sxs-lookup"><span data-stu-id="841a2-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="841a2-113">SDK</span><span class="sxs-lookup"><span data-stu-id="841a2-113">sdk</span></span>

<span data-ttu-id="841a2-114">Digitare: `object`</span><span class="sxs-lookup"><span data-stu-id="841a2-114">Type: `object`</span></span>

<span data-ttu-id="841a2-115">Specifica le informazioni sul .NET Core SDK da selezionare.</span><span class="sxs-lookup"><span data-stu-id="841a2-115">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="841a2-116">version</span><span class="sxs-lookup"><span data-stu-id="841a2-116">version</span></span>

- <span data-ttu-id="841a2-117">Digitare: `string`</span><span class="sxs-lookup"><span data-stu-id="841a2-117">Type: `string`</span></span>

- <span data-ttu-id="841a2-118">Disponibile a partire da: .NET Core 1,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="841a2-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="841a2-119">La versione del .NET Core SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="841a2-119">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="841a2-120">Questo campo:</span><span class="sxs-lookup"><span data-stu-id="841a2-120">This field:</span></span>

- <span data-ttu-id="841a2-121">Non dispone del supporto per i caratteri jolly, ovvero è necessario specificare il numero di versione completo.</span><span class="sxs-lookup"><span data-stu-id="841a2-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="841a2-122">Non supporta gli intervalli di versione.</span><span class="sxs-lookup"><span data-stu-id="841a2-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="841a2-123">Flag allowprerelease</span><span class="sxs-lookup"><span data-stu-id="841a2-123">allowPrerelease</span></span>

- <span data-ttu-id="841a2-124">Digitare: `boolean`</span><span class="sxs-lookup"><span data-stu-id="841a2-124">Type: `boolean`</span></span>

- <span data-ttu-id="841a2-125">Disponibile a partire da: .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="841a2-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="841a2-126">Indica se il resolver SDK deve prendere in considerazione le versioni provvisorie quando si seleziona la versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="841a2-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="841a2-127">Se questo valore non viene impostato in modo esplicito, il valore predefinito varia a seconda che l'esecuzione venga eseguita da Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="841a2-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="841a2-128">Se **non** si è in Visual Studio, il valore predefinito è `true` .</span><span class="sxs-lookup"><span data-stu-id="841a2-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="841a2-129">Se si usa Visual Studio, viene usato lo stato della versione non definitiva richiesta.</span><span class="sxs-lookup"><span data-stu-id="841a2-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="841a2-130">Ovvero, se si usa una versione di anteprima di Visual Studio o si imposta l'opzione **Usa anteprime del .NET Core SDK** (in **strumenti**  >  **Opzioni**  >  **ambiente**  >  **Anteprima funzionalità**), il valore predefinito è `true` ; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="841a2-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="841a2-131">rollForward</span><span class="sxs-lookup"><span data-stu-id="841a2-131">rollForward</span></span>

- <span data-ttu-id="841a2-132">Digitare: `string`</span><span class="sxs-lookup"><span data-stu-id="841a2-132">Type: `string`</span></span>

- <span data-ttu-id="841a2-133">Disponibile a partire da: .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="841a2-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="841a2-134">Criteri di rollforward da usare quando si seleziona una versione di SDK, come fallback quando manca una versione specifica dell'SDK o come direttiva per usare una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="841a2-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="841a2-135">È necessario specificare una [versione](#version) con un `rollForward` valore, a meno che non lo si stia impostando su `latestMajor` .</span><span class="sxs-lookup"><span data-stu-id="841a2-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>

<span data-ttu-id="841a2-136">Per comprendere i criteri disponibili e il relativo comportamento, prendere in considerazione le seguenti definizioni per una versione SDK nel formato `x.y.znn` :</span><span class="sxs-lookup"><span data-stu-id="841a2-136">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="841a2-137">`x`è la versione principale.</span><span class="sxs-lookup"><span data-stu-id="841a2-137">`x` is the major version.</span></span>
- <span data-ttu-id="841a2-138">`y`è la versione secondaria.</span><span class="sxs-lookup"><span data-stu-id="841a2-138">`y` is the minor version.</span></span>
- <span data-ttu-id="841a2-139">`z`è la banda della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="841a2-139">`z` is the feature band.</span></span>
- <span data-ttu-id="841a2-140">`nn`versione della patch.</span><span class="sxs-lookup"><span data-stu-id="841a2-140">`nn` is the patch version.</span></span>

<span data-ttu-id="841a2-141">La tabella seguente mostra i valori possibili per la `rollForward` chiave:</span><span class="sxs-lookup"><span data-stu-id="841a2-141">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="841a2-142">valore</span><span class="sxs-lookup"><span data-stu-id="841a2-142">Value</span></span>         | <span data-ttu-id="841a2-143">Comportamento</span><span class="sxs-lookup"><span data-stu-id="841a2-143">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="841a2-144">Usa la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="841a2-144">Uses the specified version.</span></span> <br> <span data-ttu-id="841a2-145">Se non viene trovato, viene eseguito il rollforward al livello di patch più recente.</span><span class="sxs-lookup"><span data-stu-id="841a2-145">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="841a2-146">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="841a2-146">If not found, fails.</span></span> <br><br> <span data-ttu-id="841a2-147">Questo valore è il comportamento legacy delle versioni precedenti dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="841a2-147">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="841a2-148">Usa il livello di patch più recente per la banda principale, secondaria e di funzionalità specificata.</span><span class="sxs-lookup"><span data-stu-id="841a2-148">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="841a2-149">Se non viene trovato, viene eseguito il rollforward alla successiva fascia di funzionalità superiore all'interno della stessa major/minor e viene usato il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="841a2-149">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="841a2-150">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="841a2-150">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="841a2-151">Usa il livello di patch più recente per la banda principale, secondaria e di funzionalità specificata.</span><span class="sxs-lookup"><span data-stu-id="841a2-151">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="841a2-152">Se non viene trovato, viene eseguito il rollforward alla successiva fascia di funzionalità superiore all'interno della stessa versione principale/secondaria e viene usato il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="841a2-152">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="841a2-153">Se non viene trovato, viene eseguito il rollforward alla successiva fascia secondaria e di funzionalità più alta all'interno della stessa entità e utilizza il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="841a2-153">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="841a2-154">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="841a2-154">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="841a2-155">Usa il livello di patch più recente per la banda principale, secondaria e di funzionalità specificata.</span><span class="sxs-lookup"><span data-stu-id="841a2-155">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="841a2-156">Se non viene trovato, viene eseguito il rollforward alla successiva fascia di funzionalità superiore all'interno della stessa versione principale/secondaria e viene usato il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="841a2-156">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="841a2-157">Se non viene trovato, viene eseguito il rollforward alla successiva fascia secondaria e di funzionalità più alta all'interno della stessa entità e utilizza il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="841a2-157">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="841a2-158">Se non viene trovato, viene eseguito il rollforward alla successiva fascia principale, secondaria e di funzionalità più alta e viene usato il livello di patch più recente per tale banda di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="841a2-158">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="841a2-159">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="841a2-159">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="841a2-160">Usa il livello di patch installato più recente che corrisponde alla banda principale, secondaria e di funzionalità richiesta con un livello di patch e che è maggiore o uguale al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="841a2-160">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="841a2-161">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="841a2-161">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="841a2-162">Usa la banda di funzionalità e il livello di patch più elevati che corrispondono al principale e al minore richiesti con una banda di funzionalità maggiore o uguale al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="841a2-162">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="841a2-163">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="841a2-163">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="841a2-164">Usa la versione secondaria, la banda di funzionalità e il livello di patch più elevati che corrispondono al principale richiesto con un valore secondario maggiore o uguale al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="841a2-164">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="841a2-165">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="841a2-165">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="841a2-166">Usa la .NET Core SDK installata più alta con una maggiore o uguale al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="841a2-166">Uses the highest installed .NET Core SDK with a major that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="841a2-167">Se non viene trovato, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="841a2-167">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="841a2-168">Il rollforward non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="841a2-168">Doesn't roll forward.</span></span> <span data-ttu-id="841a2-169">È necessaria una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="841a2-169">Exact match required.</span></span> |

### <a name="msbuild-sdks"></a><span data-ttu-id="841a2-170">MSBuild-SDK</span><span class="sxs-lookup"><span data-stu-id="841a2-170">msbuild-sdks</span></span>

<span data-ttu-id="841a2-171">Digitare: `object`</span><span class="sxs-lookup"><span data-stu-id="841a2-171">Type: `object`</span></span>

<span data-ttu-id="841a2-172">Consente di controllare la versione dell'SDK di progetto in un'unica posizione invece che in ogni singolo progetto.</span><span class="sxs-lookup"><span data-stu-id="841a2-172">Lets you control the project SDK version in one place rather than in each individual project.</span></span> <span data-ttu-id="841a2-173">Per ulteriori informazioni, vedere [come vengono risolti gli SDK di progetto](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span><span class="sxs-lookup"><span data-stu-id="841a2-173">For more information, see [How project SDKs are resolved](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span></span>

## <a name="examples"></a><span data-ttu-id="841a2-174">Esempi</span><span class="sxs-lookup"><span data-stu-id="841a2-174">Examples</span></span>

<span data-ttu-id="841a2-175">Nell'esempio seguente viene illustrato come non utilizzare le versioni provvisorie:</span><span class="sxs-lookup"><span data-stu-id="841a2-175">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="841a2-176">Nell'esempio seguente viene illustrato come utilizzare la versione più recente installata che è maggiore o uguale alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="841a2-176">The following example shows how to use the highest version installed that is greater or equal than the specified version.</span></span> <span data-ttu-id="841a2-177">Il codice JSON visualizzato non consente la versione dell'SDK precedente a 2.2.200 e consente 2.2.200 o qualsiasi versione successiva, inclusi 3.0.xxx e 3.1.xxx.</span><span class="sxs-lookup"><span data-stu-id="841a2-177">The JSON shown disallows any SDK version earlier than 2.2.200 and allows 2.2.200 or any later version, including 3.0.xxx and 3.1.xxx.</span></span>

```json
{
  "sdk": {
    "version": "2.2.200",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="841a2-178">Nell'esempio seguente viene illustrato come utilizzare la versione esatta specificata:</span><span class="sxs-lookup"><span data-stu-id="841a2-178">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="841a2-179">Nell'esempio seguente viene illustrato come utilizzare la versione più recente della patch e la versione di patch installata di una versione principale e secondaria specifica.</span><span class="sxs-lookup"><span data-stu-id="841a2-179">The following example shows how to use the latest feature band and patch version installed of a specific major and minor version.</span></span> <span data-ttu-id="841a2-180">Il codice JSON visualizzato non consente la versione dell'SDK precedente a 3.1.102 e consente 3.1.102 o qualsiasi versione successiva di 3.1.xxx, ad esempio 3.1.103 o 3.1.200.</span><span class="sxs-lookup"><span data-stu-id="841a2-180">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.xxx version, such as 3.1.103 or 3.1.200.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestFeature"
  }
}
```

<span data-ttu-id="841a2-181">Nell'esempio seguente viene illustrato come utilizzare la versione patch più recente installata di una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="841a2-181">The following example shows how to use the highest patch version installed of a specific version.</span></span> <span data-ttu-id="841a2-182">Il codice JSON visualizzato non consente la versione dell'SDK precedente a 3.1.102 e consente 3.1.102 o qualsiasi versione successiva di 3.1.1 XX, ad esempio 3.1.103 o 3.1.199.</span><span class="sxs-lookup"><span data-stu-id="841a2-182">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.1xx version, such as 3.1.103 or 3.1.199.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="841a2-183">global.json e interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="841a2-183">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="841a2-184">È utile comprendere quali versioni dell'SDK sono installate nel computer per impostarne una nel file *Global. JSON* .</span><span class="sxs-lookup"><span data-stu-id="841a2-184">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="841a2-185">Per altre informazioni su come eseguire questa operazione, vedere [come verificare che .NET Core sia già installato](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span><span class="sxs-lookup"><span data-stu-id="841a2-185">For more information on how to do that, see [How to check that .NET Core is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="841a2-186">Per installare altre versioni .NET Core SDK nel computer, visitare la pagina [download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .</span><span class="sxs-lookup"><span data-stu-id="841a2-186">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="841a2-187">È possibile creare un nuovo file *global.json* nella directory corrente eseguendo il comando [dotnet new](dotnet-new.md), in modo simile al seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="841a2-187">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="841a2-188">Regole di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="841a2-188">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="841a2-189">Le regole di corrispondenza sono regolate dal `dotnet.exe` punto di ingresso, che è comune in tutti i runtime installati di .net core installati.</span><span class="sxs-lookup"><span data-stu-id="841a2-189">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET Core installed runtimes.</span></span> <span data-ttu-id="841a2-190">Le regole di corrispondenza per la versione installata più recente del runtime di .NET Core vengono usate quando si hanno più runtime installati side-by-side.</span><span class="sxs-lookup"><span data-stu-id="841a2-190">The matching rules for the latest installed version of the .NET Core Runtime are used when you have multiple runtimes installed side-by-side.</span></span>

## <a name="net-core-3x"></a>[<span data-ttu-id="841a2-191">.NET Core 3.x</span><span class="sxs-lookup"><span data-stu-id="841a2-191">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="841a2-192">A partire da .NET Core 3,0, quando si determina la versione dell'SDK da usare sono valide le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="841a2-192">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="841a2-193">Se non viene trovato alcun file *Global. JSON* oppure il file *Global. JSON* non specifica una versione dell'SDK né un `allowPrerelease` valore, viene usata la versione più recente dell'SDK installato (equivale a impostare `rollForward` su `latestMajor` ).</span><span class="sxs-lookup"><span data-stu-id="841a2-193">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="841a2-194">Il fatto che le versioni di versione non definitiva dell'SDK siano considerate dipende da come `dotnet` viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="841a2-194">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="841a2-195">Se **non** si è in Visual Studio, vengono considerate le versioni provvisorie.</span><span class="sxs-lookup"><span data-stu-id="841a2-195">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="841a2-196">Se si usa Visual Studio, viene usato lo stato della versione non definitiva richiesta.</span><span class="sxs-lookup"><span data-stu-id="841a2-196">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="841a2-197">Ovvero, se si usa una versione di anteprima di Visual Studio o si imposta l'opzione **USA** anteprime dell'opzione .NET Core SDK (in **strumenti**  >  **Opzioni**  >  **ambiente**  >  **Anteprima funzionalità**), vengono considerate le versioni preliminari; in caso contrario, vengono considerate solo le versioni di rilascio.</span><span class="sxs-lookup"><span data-stu-id="841a2-197">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="841a2-198">Se viene trovato un file *Global. JSON* che non specifica una versione dell'SDK ma specifica un `allowPrerelease` valore, viene usata la versione più recente dell'SDK installato (equivalente all'impostazione `rollForward` di su `latestMajor` ).</span><span class="sxs-lookup"><span data-stu-id="841a2-198">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="841a2-199">Se la versione più recente dell'SDK può essere release o versione preliminare dipende dal valore di `allowPrerelease` .</span><span class="sxs-lookup"><span data-stu-id="841a2-199">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="841a2-200">`true`indica che le versioni provvisorie sono considerate. `false`indica che vengono considerate solo le versioni di rilascio.</span><span class="sxs-lookup"><span data-stu-id="841a2-200">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="841a2-201">Se viene trovato un file *Global. JSON* che specifica una versione dell'SDK:</span><span class="sxs-lookup"><span data-stu-id="841a2-201">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="841a2-202">Se non `rollFoward` è impostato alcun valore, utilizza `latestPatch` come criterio predefinito `rollForward` .</span><span class="sxs-lookup"><span data-stu-id="841a2-202">If no `rollFoward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="841a2-203">In caso contrario, controllare ogni valore e il relativo comportamento nella sezione [rollforward](#rollforward) .</span><span class="sxs-lookup"><span data-stu-id="841a2-203">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="841a2-204">Se vengono considerate le versioni provvisorie e qual è il comportamento predefinito quando `allowPrerelease` non è impostato è descritto nella sezione [flag allowprerelease](#allowprerelease) .</span><span class="sxs-lookup"><span data-stu-id="841a2-204">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2x"></a>[<span data-ttu-id="841a2-205">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="841a2-205">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="841a2-206">In .NET Core 2. x SDK, quando si determina la versione dell'SDK da usare, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="841a2-206">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="841a2-207">Se non vengono trovati file *global.json* o *global.json* non specifica una versione SDK, viene usata l'ultima versione SDK installata.</span><span class="sxs-lookup"><span data-stu-id="841a2-207">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="841a2-208">La versione più recente dell'SDK può essere release o prerelease. il numero di versione più alto prevale.</span><span class="sxs-lookup"><span data-stu-id="841a2-208">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="841a2-209">Se *global.json* specifica una versione SDK:</span><span class="sxs-lookup"><span data-stu-id="841a2-209">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="841a2-210">Se la versione SDK indicata è presente nel computer, si usa quella versione.</span><span class="sxs-lookup"><span data-stu-id="841a2-210">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="841a2-211">Se la versione SDK specificata non è presente nel computer, viene usata la **versione patch** SDK installata più recente.</span><span class="sxs-lookup"><span data-stu-id="841a2-211">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="841a2-212">La versione più recente della **patch** SDK installata può essere release o versione preliminare-il numero di versione più alto prevale.</span><span class="sxs-lookup"><span data-stu-id="841a2-212">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="841a2-213">In .NET Core 2.1 e versioni successive, le **versioni patch** inferiori alla **versione patch** specificata vengono ignorate nella selezione del SDK.</span><span class="sxs-lookup"><span data-stu-id="841a2-213">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="841a2-214">Se non è possibile trovare la versione SDK specificata e una **versione patch** SDK appropriata, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="841a2-214">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="841a2-215">La versione dell'SDK è costituita dalle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="841a2-215">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="841a2-216">La **versione definitiva** di .NET Core SDK è rappresentata dalla prima cifra (`x`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive.</span><span class="sxs-lookup"><span data-stu-id="841a2-216">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="841a2-217">In generale, .NET Core SDK ha un ciclo di rilascio più veloce rispetto a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="841a2-217">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="841a2-218">La **versione patch** è definita dalle ultime due cifre (`yz`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive.</span><span class="sxs-lookup"><span data-stu-id="841a2-218">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="841a2-219">Ad esempio, se si specifica `2.1.300` come versione SDK, la selezione del SDK può arrivare fino a `2.1.399` ma `2.1.400` non è considerata una versione patch per `2.1.300`.</span><span class="sxs-lookup"><span data-stu-id="841a2-219">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="841a2-220">Le versioni di .NET core SDK da `2.1.100` a `2.1.201` sono state rilasciate durante la transizione tra gli schemi dei numeri di versione e non gestiscono correttamente la notazione `xyz`.</span><span class="sxs-lookup"><span data-stu-id="841a2-220">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="841a2-221">Se queste versioni vengono specificate nel file *global.json*, è consigliabile verificare che tali versioni siano presenti nei computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="841a2-221">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshoot-build-warnings"></a><span data-ttu-id="841a2-222">Risolvere i problemi relativi agli avvisi di compilazione</span><span class="sxs-lookup"><span data-stu-id="841a2-222">Troubleshoot build warnings</span></span>

* <span data-ttu-id="841a2-223">L'avviso seguente indica che il progetto è stato compilato utilizzando una versione provvisoria del .NET Core SDK:</span><span class="sxs-lookup"><span data-stu-id="841a2-223">The following warning indicates that your project was compiled using a prerelease version of the .NET Core SDK:</span></span>

  > <span data-ttu-id="841a2-224">Si sta lavorando con una versione di anteprima di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="841a2-224">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="841a2-225">È possibile definire la versione SDK tramite un file global.json nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="841a2-225">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="841a2-226">Altre informazioni <https://go.microsoft.com/fwlink/?linkid=869452> .</span><span class="sxs-lookup"><span data-stu-id="841a2-226">More at <https://go.microsoft.com/fwlink/?linkid=869452>.</span></span>

  <span data-ttu-id="841a2-227">Le versioni di .NET Core SDK hanno una storia e un impegno di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="841a2-227">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="841a2-228">Tuttavia, se non si vuole usare una versione provvisoria, controllare le diverse strategie che è possibile usare con .NET Core 3,0 SDK o una versione successiva nella sezione [flag allowprerelease](#allowprerelease) .</span><span class="sxs-lookup"><span data-stu-id="841a2-228">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="841a2-229">Per i computer in cui non è mai stato installato un runtime o un SDK di .NET Core 3,0 o versione successiva, è necessario creare un file *Global. JSON* e specificare la versione esatta che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="841a2-229">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

* <span data-ttu-id="841a2-230">L'avviso seguente indica che il progetto è destinato a EF Core 1,0 o 1,1, che non è compatibile con .NET Core 2,1 SDK e versioni successive:</span><span class="sxs-lookup"><span data-stu-id="841a2-230">The following warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions:</span></span>

  > <span data-ttu-id="841a2-231">Progetto di avvio '{startupProject}' framework di destinazione '.NETCoreApp' versione '{targetFrameworkVersion}'.</span><span class="sxs-lookup"><span data-stu-id="841a2-231">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="841a2-232">Questa versione degli strumenti della riga di comando di Entity Framework Core .NET supporta solo la versione 2.0 o successive.</span><span class="sxs-lookup"><span data-stu-id="841a2-232">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="841a2-233">Per informazioni sull'utilizzo di versioni precedenti degli strumenti di, vedere <https://go.microsoft.com/fwlink/?linkid=871254> .</span><span class="sxs-lookup"><span data-stu-id="841a2-233">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254>.</span></span>

  <span data-ttu-id="841a2-234">A partire da .NET Core 2.1 SDK (versione 2.1.300), il comando `dotnet ef` è incluso nell'SDK.</span><span class="sxs-lookup"><span data-stu-id="841a2-234">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="841a2-235">Per compilare il progetto, installare .NET Core 2,0 SDK (versione 2.1.201) o versioni precedenti nel computer e definire la versione dell'SDK desiderata usando il file *Global. JSON* .</span><span class="sxs-lookup"><span data-stu-id="841a2-235">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) or earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="841a2-236">Per altre informazioni sul comando `dotnet ef`, vedere [Strumenti da riga di comando di EF Core .NET](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="841a2-236">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="841a2-237">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="841a2-237">See also</span></span>

- [<span data-ttu-id="841a2-238">Come vengono risolti gli SDK di progetto</span><span class="sxs-lookup"><span data-stu-id="841a2-238">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
