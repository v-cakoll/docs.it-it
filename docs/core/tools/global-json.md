---
title: panoramica di global.json
description: Informazioni su come usare il file global.json per impostare la versione di .NET Core SDK durante l'esecuzione dei comandi dell'interfaccia della riga di comando di .NET Core.
ms.date: 12/03/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 4da703266e98b209cdd031f4ea856b4d7c83930c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714165"
---
# <a name="globaljson-overview"></a><span data-ttu-id="77618-103">panoramica di global.json</span><span class="sxs-lookup"><span data-stu-id="77618-103">global.json overview</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

<span data-ttu-id="77618-104">Il file *global.json* consente di definire la versione di .NET Core SDK usata quando si eseguono comandi dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77618-104">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="77618-105">La selezione di .NET Core SDK è indipendente dalla specifica del runtime delle destinazioni del progetto.</span><span class="sxs-lookup"><span data-stu-id="77618-105">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="77618-106">La versione di .NET Core SDK indica quali versioni degli strumenti dell'interfaccia della riga di comando di .NET Core vengono usate.</span><span class="sxs-lookup"><span data-stu-id="77618-106">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span> <span data-ttu-id="77618-107">In generale, si desidera usare la versione più recente degli strumenti, quindi il file *global.json* non è necessario.</span><span class="sxs-lookup"><span data-stu-id="77618-107">In general, you want to use the latest version of the tools, so no *global.json* file is needed.</span></span>

<span data-ttu-id="77618-108">Per altre informazioni su come specificare il runtime, vedere [Framework di destinazione](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="77618-108">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="77618-109">.NET Core SDK cerca un file *global.json* nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.</span><span class="sxs-lookup"><span data-stu-id="77618-109">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="77618-110">schema global.json</span><span class="sxs-lookup"><span data-stu-id="77618-110">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="77618-111">SDK</span><span class="sxs-lookup"><span data-stu-id="77618-111">sdk</span></span>

<span data-ttu-id="77618-112">Tipo: Object</span><span class="sxs-lookup"><span data-stu-id="77618-112">Type: Object</span></span>

<span data-ttu-id="77618-113">Specifica le informazioni sul .NET Core SDK da selezionare.</span><span class="sxs-lookup"><span data-stu-id="77618-113">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="77618-114">Versione di</span><span class="sxs-lookup"><span data-stu-id="77618-114">version</span></span>

<span data-ttu-id="77618-115">Tipo: String</span><span class="sxs-lookup"><span data-stu-id="77618-115">Type: String</span></span>

<span data-ttu-id="77618-116">La versione del .NET Core SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="77618-116">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="77618-117">Si noti che questo campo:</span><span class="sxs-lookup"><span data-stu-id="77618-117">Note that this field:</span></span>

- <span data-ttu-id="77618-118">Non dispone di supporto di caratteri jolly, vale a dire che è necessario specificare il numero di versione completo.</span><span class="sxs-lookup"><span data-stu-id="77618-118">Doesn't have globbing support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="77618-119">Non supporta gli intervalli di versione.</span><span class="sxs-lookup"><span data-stu-id="77618-119">Doesn't support version ranges.</span></span>

<span data-ttu-id="77618-120">L'esempio seguente illustra il contenuto di un file *global.json*:</span><span class="sxs-lookup"><span data-stu-id="77618-120">The following example shows the contents of a *global.json* file:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="77618-121">global.json e interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="77618-121">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="77618-122">È utile sapere quali versioni sono disponibili per configurarne una nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="77618-122">It's helpful to know which versions are available in order to set one in the *global.json* file.</span></span> <span data-ttu-id="77618-123">È possibile trovare l'elenco completo degli SDK disponibili supportati nella pagina [scaricare .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .</span><span class="sxs-lookup"><span data-stu-id="77618-123">You can find the full list of supported available SDKs at the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span> <span data-ttu-id="77618-124">A partire da .NET Core 2.1 SDK, è possibile eseguire il comando seguente per verificare quali versioni dell'SDK sono già installate nel computer:</span><span class="sxs-lookup"><span data-stu-id="77618-124">Starting with .NET Core 2.1 SDK, you can run the following command to verify which SDK versions are already installed on your machine:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="77618-125">Per installare altre versioni .NET Core SDK nel computer, visitare la pagina [download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .</span><span class="sxs-lookup"><span data-stu-id="77618-125">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="77618-126">È possibile creare un nuovo file *global.json* nella directory corrente eseguendo il comando [dotnet new](dotnet-new.md), in modo simile al seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="77618-126">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a><span data-ttu-id="77618-127">Regole di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="77618-127">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="77618-128">Le regole di corrispondenza sono regolate da apphost, che fa parte del runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77618-128">The matching rules are governed by the apphost, which is part of the .NET Core runtime.</span></span>
> <span data-ttu-id="77618-129">Quando si dispone di più runtime installati side-by-side, viene usata la versione più recente dell'host.</span><span class="sxs-lookup"><span data-stu-id="77618-129">The latest version of the host is used when you have multiple runtimes installed side-by-side.</span></span>

<span data-ttu-id="77618-130">A partire da .NET Core 2.0, le regole seguenti si applicano per stabilire quale versione SDK usare:</span><span class="sxs-lookup"><span data-stu-id="77618-130">Starting with .NET Core 2.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="77618-131">Se non vengono trovati file *global.json* o *global.json* non specifica una versione SDK, viene usata l'ultima versione SDK installata.</span><span class="sxs-lookup"><span data-stu-id="77618-131">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="77618-132">L'ultima versione SDK può essere rilasciata o pre-rilasciata: il numero di versione più alto ha la priorità.</span><span class="sxs-lookup"><span data-stu-id="77618-132">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>
- <span data-ttu-id="77618-133">Se *global.json* specifica una versione SDK:</span><span class="sxs-lookup"><span data-stu-id="77618-133">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="77618-134">Se la versione SDK indicata è presente nel computer, si usa quella versione.</span><span class="sxs-lookup"><span data-stu-id="77618-134">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="77618-135">Se la versione SDK specificata non è presente nel computer, viene usata la **versione patch** SDK installata più recente.</span><span class="sxs-lookup"><span data-stu-id="77618-135">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="77618-136">L'ultima **versione patch** SDK installata può essere rilasciata o pre-rilasciata: il numero di versione più alto ha la priorità.</span><span class="sxs-lookup"><span data-stu-id="77618-136">Latest installed SDK **patch version** can be either release or pre-release - the highest version number wins.</span></span> <span data-ttu-id="77618-137">In .NET Core 2.1 e versioni successive, le **versioni patch** inferiori alla **versione patch** specificata vengono ignorate nella selezione del SDK.</span><span class="sxs-lookup"><span data-stu-id="77618-137">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="77618-138">Se non è possibile trovare la versione SDK specificata e una **versione patch** SDK appropriata, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="77618-138">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="77618-139">La versione SDK è attualmente costituita dalle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="77618-139">The SDK version is currently composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="77618-140">La **versione definitiva** di .NET Core SDK è rappresentata dalla prima cifra (`x`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive.</span><span class="sxs-lookup"><span data-stu-id="77618-140">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="77618-141">In generale, .NET Core SDK ha un ciclo di rilascio più veloce rispetto a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77618-141">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="77618-142">La **versione patch** è definita dalle ultime due cifre (`yz`) nell'ultima parte del numero (`xyz`) per le versioni SDK 2.1.100 e successive.</span><span class="sxs-lookup"><span data-stu-id="77618-142">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="77618-143">Ad esempio, se si specifica `2.1.300` come versione SDK, la selezione del SDK può arrivare fino a `2.1.399` ma `2.1.400` non è considerata una versione patch per `2.1.300`.</span><span class="sxs-lookup"><span data-stu-id="77618-143">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="77618-144">Le versioni di .NET core SDK da `2.1.100` a `2.1.201` sono state rilasciate durante la transizione tra gli schemi dei numeri di versione e non gestiscono correttamente la notazione `xyz`.</span><span class="sxs-lookup"><span data-stu-id="77618-144">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="77618-145">Se queste versioni vengono specificate nel file *global.json*, è consigliabile verificare che tali versioni siano presenti nei computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="77618-145">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

<span data-ttu-id="77618-146">Con .NET Core SDK 1.x, se è stata specificata una versione e non è stata trovata alcuna corrispondenza esatta, è stata usata la versione SDK più recente.</span><span class="sxs-lookup"><span data-stu-id="77618-146">With .NET Core SDK 1.x, if you specified a version and no exact match was found, the latest installed SDK version was used.</span></span> <span data-ttu-id="77618-147">L'ultima versione SDK può essere rilasciata o pre-rilasciata: il numero di versione più alto ha la priorità.</span><span class="sxs-lookup"><span data-stu-id="77618-147">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="77618-148">Risoluzione dei problemi relativi agli avvisi di compilazione</span><span class="sxs-lookup"><span data-stu-id="77618-148">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="77618-149">Si sta lavorando con una versione di anteprima di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="77618-149">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="77618-150">È possibile definire la versione SDK tramite un file global.json nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="77618-150">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="77618-151">Per altre informazioni, vedere <https://go.microsoft.com/fwlink/?linkid=869452></span><span class="sxs-lookup"><span data-stu-id="77618-151">More at <https://go.microsoft.com/fwlink/?linkid=869452></span></span>

<span data-ttu-id="77618-152">Questo avviso indica che il progetto è stato compilato usando una versione di anteprima di .NET Core SDK, come illustrato nella sezione [Regole di corrispondenza](#matching-rules).</span><span class="sxs-lookup"><span data-stu-id="77618-152">This warning indicates that your project is being compiled using a preview version of the .NET Core SDK, as explained in the [Matching rules](#matching-rules) section.</span></span> <span data-ttu-id="77618-153">Le versioni di .NET Core SDK hanno una storia e un impegno di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="77618-153">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="77618-154">Tuttavia, se non si vuole usare una versione di anteprima, aggiungere un file *global.json* alla struttura gerarchica del progetto per specificare la versione SDK da usare e selezionare `dotnet --list-sdks` per confermare che la versione è installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="77618-154">However, if you don't want to use a preview version, add a *global.json* file to your project hierarchy structure to specify which SDK version to use, and use `dotnet --list-sdks` to confirm that the version is installed on your machine.</span></span> <span data-ttu-id="77618-155">Quando viene rilasciata una nuova versione, usare la nuova versione, rimuovere il file *global.json* o aggiornarlo per usare la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="77618-155">When a new version is released, to use the new version, either remove the *global.json* file or update it to use the newer version.</span></span>

> [!WARNING]
> <span data-ttu-id="77618-156">Progetto di avvio '{startupProject}' framework di destinazione '.NETCoreApp' versione '{targetFrameworkVersion}'.</span><span class="sxs-lookup"><span data-stu-id="77618-156">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="77618-157">Questa versione degli strumenti della riga di comando di Entity Framework Core .NET supporta solo la versione 2.0 o successive.</span><span class="sxs-lookup"><span data-stu-id="77618-157">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="77618-158">Per informazioni sull'uso di versioni precedenti degli strumenti, vedere <https://go.microsoft.com/fwlink/?linkid=871254></span><span class="sxs-lookup"><span data-stu-id="77618-158">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254></span></span>

<span data-ttu-id="77618-159">A partire da .NET Core 2.1 SDK (versione 2.1.300), il comando `dotnet ef` è incluso nell'SDK.</span><span class="sxs-lookup"><span data-stu-id="77618-159">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="77618-160">Questo avviso indica che il progetto è destinato a EF Core 1.0 o 1.1, che non è compatibile con .NET Core 2.1 SDK e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="77618-160">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions.</span></span> <span data-ttu-id="77618-161">Per compilare il progetto, installare .NET Core 2.0 SDK (versione 2.1.201) e versioni precedenti nel computer e definire la versione dell'SDK desiderata usando il file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="77618-161">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) and earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="77618-162">Per altre informazioni sul comando `dotnet ef`, vedere [Strumenti da riga di comando di EF Core .NET](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="77618-162">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="77618-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77618-163">See also</span></span>

- [<span data-ttu-id="77618-164">Come vengono risolti gli SDK di progetto</span><span class="sxs-lookup"><span data-stu-id="77618-164">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
