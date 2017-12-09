---
title: -langversion (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: "33"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d3d59f63102ccf3c1d54e4028635c8daad56164
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2017
---
# <a name="langversion-c-compiler-options"></a><span data-ttu-id="13334-102">/langversion (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="13334-102">/langversion (C# Compiler Options)</span></span>
<span data-ttu-id="13334-103">Imposta il compilatore in modo da accettare solo sintassi inclusa nella specifica di linguaggio C# selezionata.</span><span class="sxs-lookup"><span data-stu-id="13334-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13334-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13334-104">Syntax</span></span>  
  
```console  
/langversion:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="13334-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="13334-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="13334-106">Di seguito vengono illustrati i valori validi.</span><span class="sxs-lookup"><span data-stu-id="13334-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="13334-107">Opzione</span><span class="sxs-lookup"><span data-stu-id="13334-107">Option</span></span>|<span data-ttu-id="13334-108">Significato</span><span class="sxs-lookup"><span data-stu-id="13334-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="13334-109">default</span><span class="sxs-lookup"><span data-stu-id="13334-109">default</span></span>|<span data-ttu-id="13334-110">Il compilatore accetta tutte le sintassi di linguaggio valide.</span><span class="sxs-lookup"><span data-stu-id="13334-110">The compiler accepts all valid language syntax that it can support.</span></span> <span data-ttu-id="13334-111"><sup id="TDefault">[Default](#FDefault)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-111"><sup id="TDefault">[Default](#FDefault)</sup></span></span>| 
|<span data-ttu-id="13334-112">ISO-1</span><span class="sxs-lookup"><span data-stu-id="13334-112">ISO-1</span></span>|<span data-ttu-id="13334-113">Il compilatore accetta solo la sintassi inclusa nella specifica di linguaggio ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-113">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  
|<span data-ttu-id="13334-114">ISO-2</span><span class="sxs-lookup"><span data-stu-id="13334-114">ISO-2</span></span>|<span data-ttu-id="13334-115">Il compilatore accetta solo la sintassi inclusa nella specifica di linguaggio ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-115">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="13334-116">3</span><span class="sxs-lookup"><span data-stu-id="13334-116">3</span></span>|<span data-ttu-id="13334-117">Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione inferiore <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-117">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="13334-118">4</span><span class="sxs-lookup"><span data-stu-id="13334-118">4</span></span>|<span data-ttu-id="13334-119">Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione inferiore <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-119">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="13334-120">5</span><span class="sxs-lookup"><span data-stu-id="13334-120">5</span></span>|<span data-ttu-id="13334-121">Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione inferiore <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-121">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="13334-122">6</span><span class="sxs-lookup"><span data-stu-id="13334-122">6</span></span>|<span data-ttu-id="13334-123">Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione inferiore <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-123">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="13334-124">7</span><span class="sxs-lookup"><span data-stu-id="13334-124">7</span></span>|<span data-ttu-id="13334-125">Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione inferiore <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-125">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="13334-126">latest</span><span class="sxs-lookup"><span data-stu-id="13334-126">latest</span></span>|<span data-ttu-id="13334-127">Il compilatore accetta tutte le sintassi di linguaggio valide.</span><span class="sxs-lookup"><span data-stu-id="13334-127">The compiler accepts all valid language syntax that it can support.</span></span> <span data-ttu-id="13334-128"><sup id="TLatest">[Latest](#FLatest)</sup></span><span class="sxs-lookup"><span data-stu-id="13334-128"><sup id="TLatest">[Latest](#FLatest)</sup></span></span>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a><span data-ttu-id="13334-129">Note</span><span class="sxs-lookup"><span data-stu-id="13334-129">Remarks</span></span>  
 <span data-ttu-id="13334-130">I metadati a cui viene fatto riferimento nell'applicazione C# non sono soggetti all'opzione del compilatore **/langversion**.</span><span class="sxs-lookup"><span data-stu-id="13334-130">Metadata referenced by your C# application is not subject to **/langversion** compiler option.</span></span>  
  
 <span data-ttu-id="13334-131">Poiché ogni versione del compilatore C# contiene estensioni alla specifica del linguaggio, **/langversion** non fornisce la funzionalità equivalente di una versione precedente del compilatore.</span><span class="sxs-lookup"><span data-stu-id="13334-131">Because each version of the C# compiler contains extensions to the language specification, **/langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  
 
 <span data-ttu-id="13334-132">Inoltre, anche se gli aggiornamenti di versione di C# coincidono in genere con le versioni principali di .Net Framework, la nuova sintassi e le nuove funzionalità non sono necessariamente correlate alla versione specifica di Framework.</span><span class="sxs-lookup"><span data-stu-id="13334-132">Additionally, while C# version updates generally coincide with major .Net Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="13334-133">Sebbene le nuove funzionalità richiedano un nuovo aggiornamento del compilatore, anch'esso rilasciato insieme alla revisione di C#, ogni funzionalità specifica presenta requisiti minimi in termini di API .Net o Common Language Runtime che ne consentono l'esecuzione in versioni di Framework di livello inferiore, inclusi pacchetti NuGet o altre librerie.</span><span class="sxs-lookup"><span data-stu-id="13334-133">While the new features will definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .Net API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="13334-134">Indipendentemente dall'impostazione di **/langversion** specificata, per creare il file con estensione exe o dll verrà usata la versione corrente di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="13334-134">Regardless of which **/langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="13334-135">Un'eccezione è costituita dagli assembly Friend e da [/moduleassemblyname (opzione del compilatore C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), che vengono eseguiti in **/langversion: ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="13334-135">One exception is friend assemblies and [/moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **/langversion:ISO-1**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="13334-136">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="13334-136">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="13334-137">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="13334-137">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="13334-138">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="13334-138">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="13334-139">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="13334-139">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="13334-140">Modificare la proprietà **Versione linguaggio**.</span><span class="sxs-lookup"><span data-stu-id="13334-140">Modify the **Language Version** property.</span></span>  
  
 <span data-ttu-id="13334-141">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="13334-141">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="13334-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13334-142">See Also</span></span>  
 [<span data-ttu-id="13334-143">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="13334-143">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="13334-144">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="13334-144">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a><span data-ttu-id="13334-145">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="13334-145">C# Language Specification</span></span>
 <span data-ttu-id="13334-146">[Informazioni di riferimento sulla specifica di linguaggio C#](../../../csharp/language-reference/language-specification/index.md): .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="13334-146">[C# Language Specification Reference](../../../csharp/language-reference/language-specification/index.md) : .NET Foundation</span></span>  
 <span data-ttu-id="13334-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) Information Technology -- Specifica del linguaggio C#: Catalogo ISO</span><span class="sxs-lookup"><span data-stu-id="13334-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="13334-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) Information Technology -- Specifica del linguaggio C#: Catalogo ISO</span><span class="sxs-lookup"><span data-stu-id="13334-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="13334-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 in formato PDF: Standard ISO disponibili liberamente</span><span class="sxs-lookup"><span data-stu-id="13334-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 in PDF format : ISO Freely Available Standards</span></span>  
 <span data-ttu-id="13334-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) Versione 3.0 della specifica del linguaggio C#: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="13334-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# Language Specification Version 3.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="13334-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) Standard ECMA-334, quarta edizione</span><span class="sxs-lookup"><span data-stu-id="13334-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) Standard ECMA-334 4th Edition</span></span>    
 <span data-ttu-id="13334-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) Versione 5.0 della specifica del linguaggio C#: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="13334-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# Language Specification Version 5.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="13334-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) Versione 6 della specifica del linguaggio C# - Bozza non ufficiale: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="13334-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# Language Specification Version 6 - Unofficial Draft : .NET Foundation</span></span>  
 <span data-ttu-id="13334-154">C# 7.0 (attualmente non disponibile)</span><span class="sxs-lookup"><span data-stu-id="13334-154">C# 7.0 (not currently available)</span></span>  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="13334-155">Versione minima del compilatore necessaria per supportare tutte le funzionalità del linguaggio</span><span class="sxs-lookup"><span data-stu-id="13334-155">Minimum compiler version needed to support all language features</span></span>   
<span data-ttu-id="13334-156">[↩](#TDefault)<a name="FDefault">Predefinita</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 o compilatore di .Net Framework 1.0 in bundle</span><span class="sxs-lookup"><span data-stu-id="13334-156">[↩](#TDefault)<a name="FDefault">Default</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 or bundled .Net Framework 1.0 compiler</span></span>     
<span data-ttu-id="13334-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 o compilatore di .Net Framework 2.0 in bundle</span><span class="sxs-lookup"><span data-stu-id="13334-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .Net Framework 2.0 compiler</span></span>    
<span data-ttu-id="13334-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 o compilatore di .Net Framework 3.5 in bundle</span><span class="sxs-lookup"><span data-stu-id="13334-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .Net Framework 3.5 compiler</span></span>    
<span data-ttu-id="13334-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 o compilatore di .Net Framework 4.0 in bundle</span><span class="sxs-lookup"><span data-stu-id="13334-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .Net Framework 4.0 compiler</span></span>    
<span data-ttu-id="13334-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 o compilatore di .Net Framework 4.5 in bundle</span><span class="sxs-lookup"><span data-stu-id="13334-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .Net Framework 4.5 compiler</span></span>    
<span data-ttu-id="13334-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="13334-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>    
<span data-ttu-id="13334-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="13334-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017</span></span>   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
