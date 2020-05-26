---
title: -langversion (opzioni del compilatore C#)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 408b2fb1f19f872db675321601ebc1b0c921044b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802941"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="afec3-102">-langversion (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="afec3-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="afec3-103">Imposta il compilatore in modo da accettare solo sintassi inclusa nella specifica di linguaggio C# selezionata.</span><span class="sxs-lookup"><span data-stu-id="afec3-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="afec3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afec3-104">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="afec3-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="afec3-105">Arguments</span></span>

`option`

<span data-ttu-id="afec3-106">I valori seguenti sono validi:</span><span class="sxs-lookup"><span data-stu-id="afec3-106">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="afec3-107">La versione del linguaggio predefinita dipende dal framework di destinazione per l'applicazione e dalla versione dell'SDK o di Visual Studio installata.</span><span class="sxs-lookup"><span data-stu-id="afec3-107">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="afec3-108">Tali regole sono definite nell'articolo [configurazione della versione della lingua](../configure-language-version.md#defaults) .</span><span class="sxs-lookup"><span data-stu-id="afec3-108">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="afec3-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="afec3-109">Remarks</span></span>

<span data-ttu-id="afec3-110">I metadati a cui viene fatto riferimento nell'applicazione C# non sono soggetti all'opzione del compilatore **-langversion**.</span><span class="sxs-lookup"><span data-stu-id="afec3-110">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="afec3-111">Poiché ogni versione del compilatore C# contiene estensioni per la specifica del linguaggio, **-langversion** non offre la funzionalità equivalente di una versione precedente del compilatore.</span><span class="sxs-lookup"><span data-stu-id="afec3-111">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="afec3-112">Inoltre, mentre gli aggiornamenti di versione di C# coincidono in genere con le versioni principali di .NET Framework, la nuova sintassi e le nuove funzionalità non sono necessariamente correlate alla versione specifica del framework.</span><span class="sxs-lookup"><span data-stu-id="afec3-112">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="afec3-113">Sebbene le nuove funzionalità richiedano un nuovo aggiornamento del compilatore, anch'esso rilasciato insieme alla revisione di C#, ogni funzionalità specifica presenta requisiti minimi in termini di API .NET o Common Language Runtime che ne consentono l'esecuzione in versioni di Framework di livello inferiore, inclusi pacchetti NuGet o altre librerie.</span><span class="sxs-lookup"><span data-stu-id="afec3-113">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="afec3-114">Indipendentemente dall'impostazione di **langversion** usata, usare la versione corrente del Common Language Runtime per creare il file con estensione exe o dll.</span><span class="sxs-lookup"><span data-stu-id="afec3-114">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="afec3-115">Un'eccezione è costituita dagli assembly Friend e [-moduleassemblyname (opzione del compilatore C#)](./moduleassemblyname-compiler-option.md), che funziona in **-langversion: ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="afec3-115">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="afec3-116">Per altri modi per specificare la versione del linguaggio C#, vedere l'articolo [selezionare la versione del linguaggio c#](../configure-language-version.md) .</span><span class="sxs-lookup"><span data-stu-id="afec3-116">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="afec3-117">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="afec3-117">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="afec3-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="afec3-118">C# language specification</span></span>

| <span data-ttu-id="afec3-119">Versione</span><span class="sxs-lookup"><span data-stu-id="afec3-119">Version</span></span>          | <span data-ttu-id="afec3-120">Collegamento</span><span class="sxs-lookup"><span data-stu-id="afec3-120">Link</span></span>                       | <span data-ttu-id="afec3-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afec3-121">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="afec3-122">C# 7.0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="afec3-122">C# 7.0 and later</span></span> |                            | <span data-ttu-id="afec3-123">Attualmente non disponibile</span><span class="sxs-lookup"><span data-stu-id="afec3-123">Not currently available</span></span>                                                 |
| <span data-ttu-id="afec3-124">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="afec3-124">C# 6.0</span></span>           | <span data-ttu-id="afec3-125">[Collegamento][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="afec3-125">[Link][csharp-6]</span></span>           | <span data-ttu-id="afec3-126">Specifica del linguaggio C# versione 6 - Bozza non ufficiale: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="afec3-126">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="afec3-127">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="afec3-127">C# 5.0</span></span>           | <span data-ttu-id="afec3-128">[Scarica il PDF][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="afec3-128">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="afec3-129">Standard ECMA-334, quinta edizione</span><span class="sxs-lookup"><span data-stu-id="afec3-129">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="afec3-130">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="afec3-130">C# 3.0</span></span>           | <span data-ttu-id="afec3-131">[Scaricare DOC][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="afec3-131">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="afec3-132">Specifica del linguaggio C# versione 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="afec3-132">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="afec3-133">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="afec3-133">C# 2.0</span></span>           | <span data-ttu-id="afec3-134">[Scarica il PDF][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="afec3-134">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="afec3-135">Standard ECMA-334, quarta edizione</span><span class="sxs-lookup"><span data-stu-id="afec3-135">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="afec3-136">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="afec3-136">C# 1.2</span></span>           | <span data-ttu-id="afec3-137">[Scaricare DOC][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="afec3-137">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="afec3-138">Specifica del linguaggio C# versione 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="afec3-138">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="afec3-139">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="afec3-139">C# 1.0</span></span>           | <span data-ttu-id="afec3-140">[Scaricare DOC][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="afec3-140">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="afec3-141">Specifica del linguaggio C# versione 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="afec3-141">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="afec3-142">Versione minima dell'SDK necessaria per supportare tutte le funzionalità del linguaggio</span><span class="sxs-lookup"><span data-stu-id="afec3-142">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="afec3-143">La tabella seguente elenca le versioni minime dell'SDK con il compilatore C# che supporta la versione del linguaggio corrispondente:</span><span class="sxs-lookup"><span data-stu-id="afec3-143">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="afec3-144">Versione C#</span><span class="sxs-lookup"><span data-stu-id="afec3-144">C# version</span></span> | <span data-ttu-id="afec3-145">Versione minima dell'SDK</span><span class="sxs-lookup"><span data-stu-id="afec3-145">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="afec3-146">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="afec3-146">C# 8.0</span></span>     | <span data-ttu-id="afec3-147">Microsoft Visual Studio/Build Tools 2019, versione 16,3 o .NET Core 3,0 SDK</span><span class="sxs-lookup"><span data-stu-id="afec3-147">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="afec3-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="afec3-148">C# 7.3</span></span>     | <span data-ttu-id="afec3-149">Microsoft Visual Studio/Build Tools 2017 versione 15.7</span><span class="sxs-lookup"><span data-stu-id="afec3-149">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="afec3-150">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="afec3-150">C# 7.2</span></span>     | <span data-ttu-id="afec3-151">Microsoft Visual Studio/Build Tools 2017 versione 15.5</span><span class="sxs-lookup"><span data-stu-id="afec3-151">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="afec3-152">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="afec3-152">C# 7.1</span></span>     | <span data-ttu-id="afec3-153">Microsoft Visual Studio/Build Tools 2017 versione 15.3</span><span class="sxs-lookup"><span data-stu-id="afec3-153">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="afec3-154">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="afec3-154">C# 7.0</span></span>     | <span data-ttu-id="afec3-155">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="afec3-155">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="afec3-156">C# 6</span><span class="sxs-lookup"><span data-stu-id="afec3-156">C# 6</span></span>       | <span data-ttu-id="afec3-157">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="afec3-157">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="afec3-158">C# 5</span><span class="sxs-lookup"><span data-stu-id="afec3-158">C# 5</span></span>       | <span data-ttu-id="afec3-159">Microsoft Visual Studio/Build Tools 2012 o compilatore di .Net Framework 4.5 in bundle</span><span class="sxs-lookup"><span data-stu-id="afec3-159">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="afec3-160">C# 4</span><span class="sxs-lookup"><span data-stu-id="afec3-160">C# 4</span></span>       | <span data-ttu-id="afec3-161">Microsoft Visual Studio/Build Tools 2010 o compilatore di .Net Framework 4.0 in bundle</span><span class="sxs-lookup"><span data-stu-id="afec3-161">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="afec3-162">C# 3</span><span class="sxs-lookup"><span data-stu-id="afec3-162">C# 3</span></span>       | <span data-ttu-id="afec3-163">Microsoft Visual Studio/Build Tools 2008 o compilatore di .Net Framework 3.5 in bundle</span><span class="sxs-lookup"><span data-stu-id="afec3-163">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="afec3-164">C# 2</span><span class="sxs-lookup"><span data-stu-id="afec3-164">C# 2</span></span>       | <span data-ttu-id="afec3-165">Microsoft Visual Studio/Build Tools 2005 o compilatore di .Net Framework 2.0 in bundle</span><span class="sxs-lookup"><span data-stu-id="afec3-165">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="afec3-166">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="afec3-166">C# 1.0/1.2</span></span> | <span data-ttu-id="afec3-167">Microsoft Visual Studio/Build Tools .NET 2002 o bundled .NET Framework 1,0 compilatore</span><span class="sxs-lookup"><span data-stu-id="afec3-167">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="afec3-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afec3-168">See also</span></span>

- [<span data-ttu-id="afec3-169">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="afec3-169">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="afec3-170">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="afec3-170">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
