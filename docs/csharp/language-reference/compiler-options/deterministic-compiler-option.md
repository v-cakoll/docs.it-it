---
title: -deterministic (opzioni del compilatore C#)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f9aca20a3ff65d061c04a21e31db3fb5eab62ba
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45647343"
---
# <a name="-deterministic"></a><span data-ttu-id="b8603-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="b8603-102">-deterministic</span></span>

<span data-ttu-id="b8603-103">Fa sì che il compilatore generi un assembly il cui output byte per byte è identico in tutte le compilazioni se si usano input identici.</span><span class="sxs-lookup"><span data-stu-id="b8603-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="b8603-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8603-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="b8603-105">Note</span><span class="sxs-lookup"><span data-stu-id="b8603-105">Remarks</span></span>

<span data-ttu-id="b8603-106">Per impostazione predefinita, l'output del compilatore che deriva da un determinato set di input è univoco, poiché il compilatore aggiunge un timestamp e un GUID generato da numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="b8603-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="b8603-107">L'opzione `-deterministic` si usa per generare un *assembly deterministico* il cui contenuto binario è identico in tutte le compilazioni purché l'input rimanga lo stesso.</span><span class="sxs-lookup"><span data-stu-id="b8603-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="b8603-108">Il compilatore considera i seguenti input al fine del determinismo:</span><span class="sxs-lookup"><span data-stu-id="b8603-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="b8603-109">La sequenza dei parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b8603-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="b8603-110">Il contenuto del file di risposta del file RSP del compilatore.</span><span class="sxs-lookup"><span data-stu-id="b8603-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="b8603-111">La versione precisa del compilatore in uso e i relativi assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="b8603-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="b8603-112">Il percorso della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b8603-112">The current directory path.</span></span>
- <span data-ttu-id="b8603-113">Il contenuto binario di tutti i file passati in modo esplicito al compilatore direttamente o indirettamente, tra cui:</span><span class="sxs-lookup"><span data-stu-id="b8603-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
    - <span data-ttu-id="b8603-114">File di origine</span><span class="sxs-lookup"><span data-stu-id="b8603-114">Source files</span></span>
    - <span data-ttu-id="b8603-115">Assembly a cui viene fatto riferimento</span><span class="sxs-lookup"><span data-stu-id="b8603-115">Referenced assemblies</span></span>
    - <span data-ttu-id="b8603-116">Moduli a cui viene fatto riferimento</span><span class="sxs-lookup"><span data-stu-id="b8603-116">Referenced modules</span></span>
    - <span data-ttu-id="b8603-117">Risorse</span><span class="sxs-lookup"><span data-stu-id="b8603-117">Resources</span></span>
    - <span data-ttu-id="b8603-118">Il file di chiave con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="b8603-118">The strong name key file</span></span>
    - <span data-ttu-id="b8603-119">@ file di risposta</span><span class="sxs-lookup"><span data-stu-id="b8603-119">@ response files</span></span>
    - <span data-ttu-id="b8603-120">Analizzatori</span><span class="sxs-lookup"><span data-stu-id="b8603-120">Analyzers</span></span>
    - <span data-ttu-id="b8603-121">Set di regole</span><span class="sxs-lookup"><span data-stu-id="b8603-121">Rulesets</span></span>
    - <span data-ttu-id="b8603-122">File aggiuntivi che possono essere usati dagli analizzatori</span><span class="sxs-lookup"><span data-stu-id="b8603-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="b8603-123">Le impostazioni cultura correnti (per la lingua in cui vengono generati la diagnostica e i messaggi di eccezione).</span><span class="sxs-lookup"><span data-stu-id="b8603-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="b8603-124">La codifica predefinita (o la tabella codici corrente) se non è specificata la codifica.</span><span class="sxs-lookup"><span data-stu-id="b8603-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="b8603-125">L'esistenza, non esistenza e contenuto dei file nei percorsi di ricerca del compilatore (specificati, ad esempio, da `/lib` o `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="b8603-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="b8603-126">La piattaforma CLR in cui viene eseguito il compilatore.</span><span class="sxs-lookup"><span data-stu-id="b8603-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="b8603-127">Il valore di `%LIBPATH%`, che può influenzare il caricamento delle dipendenze dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="b8603-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="b8603-128">Quando le origini sono disponibili pubblicamente, la compilazione deterministica può essere usata per stabilire se un file binario viene compilato da un'origine attendibile.</span><span class="sxs-lookup"><span data-stu-id="b8603-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="b8603-129">Può anche essere utile in un sistema di compilazione continua per determinare se è necessario eseguire le istruzioni di compilazione che dipendono dalle modifiche apportate a un file binario.</span><span class="sxs-lookup"><span data-stu-id="b8603-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="b8603-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8603-130">See Also</span></span>  

- [<span data-ttu-id="b8603-131">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="b8603-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="b8603-132">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="b8603-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
