---
title: Come gestire le versioni delle dipendenze di pacchetto per .NET Core 1.0
description: Informazioni sulla gestione delle versioni delle dipendenze dei pacchetti per le app e le librerie .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.openlocfilehash: 96d154f045303e32de606475e77ab2e6b4f7bcda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33211338"
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a><span data-ttu-id="61490-103">Come gestire le versioni delle dipendenze di pacchetto per .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="61490-103">How to Manage Package Dependency Versions for .NET Core 1.0</span></span>

<span data-ttu-id="61490-104">Questo articolo descrive ciò che è necessario sapere sulle versioni dei pacchetti per le librerie e le applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="61490-104">This article covers what you need to know about package versions for your .NET Core libraries and apps.</span></span>

## <a name="glossary"></a><span data-ttu-id="61490-105">Glossario</span><span class="sxs-lookup"><span data-stu-id="61490-105">Glossary</span></span>

<span data-ttu-id="61490-106">**Correzione**: correggere le dipendenze significa usare la stessa "famiglia" di pacchetti rilasciati su NuGet per .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="61490-106">**Fix** - Fixing dependencies means you are using the same "family" of packages released on NuGet for .NET Core 1.0.</span></span>

<span data-ttu-id="61490-107">**Metapacchetto**: pacchetto NuGet che rappresenta un set di pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="61490-107">**Metapackage** - A NuGet package that represents a set of NuGet packages.</span></span>

<span data-ttu-id="61490-108">**Trimming**: rimozione dei pacchetti che non dipendono da un metapacchetto.</span><span class="sxs-lookup"><span data-stu-id="61490-108">**Trimming** - The act of removing the packages you do not depend on from a metapackage.</span></span>  <span data-ttu-id="61490-109">Queste informazioni sono importanti per gli autori di pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="61490-109">This is something relevant for NuGet package authors.</span></span>  <span data-ttu-id="61490-110">Per altre informazioni, vedere [Riduzione delle dipendenze dei pacchetti con project.json](../deploying/reducing-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="61490-110">See [Reducing Package Dependencies with project.json](../deploying/reducing-dependencies.md) for more information.</span></span> 

## <a name="fix-your-dependencies-to-net-core-10"></a><span data-ttu-id="61490-111">Correggere le dipendenze in base a .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="61490-111">Fix your dependencies to .NET Core 1.0</span></span>

<span data-ttu-id="61490-112">Per ripristinare i pacchetti e scrivere codice in modo affidabile, è importante correggere le dipendenze relative alle versioni dei pacchetti distribuiti insieme a .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="61490-112">To reliably restore packages and write reliable code, it's important that you fix your dependencies to the versions of packages shipping alongside .NET Core 1.0.</span></span>  <span data-ttu-id="61490-113">Questo significa che ogni pacchetto deve avere una sola versione senza altri qualificatori.</span><span class="sxs-lookup"><span data-stu-id="61490-113">This means every package should have a single version with no additional qualifiers.</span></span>

<span data-ttu-id="61490-114">**Esempi di pacchetti corretti in base alla versione 1.0**</span><span class="sxs-lookup"><span data-stu-id="61490-114">**Examples of packages fixed to 1.0**</span></span>

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

<span data-ttu-id="61490-115">**Esempi di pacchetti NON corretti in base alla versione 1.0**</span><span class="sxs-lookup"><span data-stu-id="61490-115">**Examples of packages that are NOT fixed to 1.0**</span></span>

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a><span data-ttu-id="61490-116">Perché questa correzione è importante?</span><span class="sxs-lookup"><span data-stu-id="61490-116">Why does this matter?</span></span>

<span data-ttu-id="61490-117">Se si correggono le dipendenze in base ai dati distribuiti con .NET Core 1.0, i pacchetti potranno interagire tra loro senza problemi.</span><span class="sxs-lookup"><span data-stu-id="61490-117">We guarantee that if you fix your dependencies to what ships alongside .NET Core 1.0, those packages will all work together.</span></span> <span data-ttu-id="61490-118">Questo comportamento non è invece garantito se i pacchetti che non vengono corretti in questo modo.</span><span class="sxs-lookup"><span data-stu-id="61490-118">There is no such guarantee if you use packages which aren't fixed in this way.</span></span>

### <a name="scenarios"></a><span data-ttu-id="61490-119">Scenari</span><span class="sxs-lookup"><span data-stu-id="61490-119">Scenarios</span></span>

<span data-ttu-id="61490-120">Anche se è disponibile un lungo elenco di tutti i pacchetti e delle relative versioni rilasciate con .NET Core 1.0, può non essere necessario esaminare l'elenco se il codice rientra in determinati scenari.</span><span class="sxs-lookup"><span data-stu-id="61490-120">Although there is a big list of all packages and their versions released with .NET Core 1.0, you may not have to look through it if your code falls under certain scenarios.</span></span>

<span data-ttu-id="61490-121">**Esistono solo dipendenze da** `NETStandard.Library`**?**</span><span class="sxs-lookup"><span data-stu-id="61490-121">**Are you depending only on** `NETStandard.Library`**?**</span></span>

<span data-ttu-id="61490-122">In questo caso, è necessario correggere il pacchetto `NETStandard.Library` in base alla versione `1.6`.</span><span class="sxs-lookup"><span data-stu-id="61490-122">If so, you should fix your `NETStandard.Library` package to version `1.6`.</span></span>  <span data-ttu-id="61490-123">Poiché si tratta di un metapacchetto curato, anche la chiusura del pacchetto viene corretta in base alla versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="61490-123">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="61490-124">**Esistono solo dipendenze da** `Microsoft.NETCore.App`**?**</span><span class="sxs-lookup"><span data-stu-id="61490-124">**Are you depending only on** `Microsoft.NETCore.App`**?**</span></span>

<span data-ttu-id="61490-125">In questo caso, è necessario correggere il pacchetto `Microsoft.NETCore.App` in base alla versione `1.0.0`.</span><span class="sxs-lookup"><span data-stu-id="61490-125">If so, you should fix your `Microsoft.NETCore.App` package to version `1.0.0`.</span></span>  <span data-ttu-id="61490-126">Poiché si tratta di un metapacchetto curato, anche la chiusura del pacchetto viene corretta in base alla versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="61490-126">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="61490-127">**Si esegue il [trimming](../deploying/reducing-dependencies.md) delle dipendenze dei metapacchetti** `NETStandard.Library` **o** `Microsoft.NETCore.App` **?**</span><span class="sxs-lookup"><span data-stu-id="61490-127">**Are you [trimming](../deploying/reducing-dependencies.md) your** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackage dependencies?**</span></span>

<span data-ttu-id="61490-128">In questo caso, è necessario verificare che il metapacchetto iniziale venga corretto in base alla versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="61490-128">If so, you should ensure that the metapackage you start with is fixed to 1.0.</span></span>  <span data-ttu-id="61490-129">Anche i singoli pacchetti da cui rimangono dipendenze dopo il trimming vengono corretti in base alla versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="61490-129">The individual packages you depend on after trimming are also fixed to 1.0.</span></span>

<span data-ttu-id="61490-130">**Esistono dipendenze da pacchetti esterni a metapacchetti** `NETStandard.Library` **o** `Microsoft.NETCore.App` **?**</span><span class="sxs-lookup"><span data-stu-id="61490-130">**Are you depending on packages outside the** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackages?**</span></span>

<span data-ttu-id="61490-131">In questo caso, è necessario correggere le altre dipendenze in base alla versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="61490-131">If so, you need to fix your other dependencies to 1.0.</span></span>  <span data-ttu-id="61490-132">Vedere le versioni di pacchetto e i numeri di build corretti alla fine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="61490-132">See the correct package versions and build numbers at the end of this article.</span></span>

### <a name="a-note-on-using-a-splat-string--when-versioning"></a><span data-ttu-id="61490-133">Nota sull'uso di una stringa con carattere jolly (\*) per il versionamento</span><span class="sxs-lookup"><span data-stu-id="61490-133">A note on using a splat string (\*) when versioning</span></span>

<span data-ttu-id="61490-134">È possibile che sia stato adottato uno schema di versionamento che usa una stringa con carattere jolly (\*) simile alla seguente: `"System.Collections":"4.0.11-*"`.</span><span class="sxs-lookup"><span data-stu-id="61490-134">You may have adopted a versioning pattern which uses a splat (\*) string like this: `"System.Collections":"4.0.11-*"`.</span></span>

<span data-ttu-id="61490-135">**Non usare stringhe di questo tipo**.</span><span class="sxs-lookup"><span data-stu-id="61490-135">**You should not do this**.</span></span>  <span data-ttu-id="61490-136">In tal caso, infatti, è possibile che vengano ripristinati pacchetti da diverse build, alcune delle quali possono non presentare alcuna corrispondenza con .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="61490-136">Using the splat string could result in restoring packages from different builds, some of which may be further along than .NET Core 1.0.</span></span>  <span data-ttu-id="61490-137">Ciò può quindi causare l'incompatibilità di alcuni pacchetti.</span><span class="sxs-lookup"><span data-stu-id="61490-137">This could then result in some packages being incompatible.</span></span>

## <a name="packages-and-version-numbers-organized-by-metapackage"></a><span data-ttu-id="61490-138">Pacchetti e numeri di versione organizzati per metapacchetto</span><span class="sxs-lookup"><span data-stu-id="61490-138">Packages and Version Numbers organized by Metapackage</span></span>

<span data-ttu-id="61490-139">[Elenco di tutti i pacchetti .NET Standard e relative versioni per 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt)</span><span class="sxs-lookup"><span data-stu-id="61490-139">[List of all .NET Standard packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span></span>

<span data-ttu-id="61490-140">[Elenco di tutti i pacchetti di runtime e relative versioni per 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt)</span><span class="sxs-lookup"><span data-stu-id="61490-140">[List of all runtime packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span></span>

<span data-ttu-id="61490-141">[Elenco di tutti i pacchetti di applicazioni .NET Core e relative versioni per 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt)</span><span class="sxs-lookup"><span data-stu-id="61490-141">[List of all .NET Core application packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span></span>
