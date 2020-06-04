---
title: -deterministic
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
ms.openlocfilehash: 0cf9aceef54998f269e9e377fe5d0a48492969c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408686"
---
# <a name="-deterministic"></a><span data-ttu-id="45fe4-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="45fe4-102">-deterministic</span></span>

<span data-ttu-id="45fe4-103">Fa sì che il compilatore generi un assembly il cui output byte per byte è identico in tutte le compilazioni se si usano input identici.</span><span class="sxs-lookup"><span data-stu-id="45fe4-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="45fe4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45fe4-104">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="45fe4-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="45fe4-105">Remarks</span></span>

<span data-ttu-id="45fe4-106">Per impostazione predefinita, l'output del compilatore che deriva da un determinato set di input è univoco, poiché il compilatore aggiunge un timestamp e un GUID generato da numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="45fe4-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="45fe4-107">L'opzione `-deterministic` si usa per generare un *assembly deterministico* il cui contenuto binario è identico in tutte le compilazioni purché l'input rimanga lo stesso.</span><span class="sxs-lookup"><span data-stu-id="45fe4-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="45fe4-108">Il compilatore considera i seguenti input al fine del determinismo:</span><span class="sxs-lookup"><span data-stu-id="45fe4-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="45fe4-109">La sequenza dei parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="45fe4-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="45fe4-110">Il contenuto del file di risposta del file RSP del compilatore.</span><span class="sxs-lookup"><span data-stu-id="45fe4-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="45fe4-111">La versione precisa del compilatore in uso e i relativi assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="45fe4-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="45fe4-112">Il percorso della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="45fe4-112">The current directory path.</span></span>
- <span data-ttu-id="45fe4-113">Il contenuto binario di tutti i file passati in modo esplicito al compilatore direttamente o indirettamente, tra cui:</span><span class="sxs-lookup"><span data-stu-id="45fe4-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="45fe4-114">File di origine</span><span class="sxs-lookup"><span data-stu-id="45fe4-114">Source files</span></span>
  - <span data-ttu-id="45fe4-115">Assembly a cui viene fatto riferimento</span><span class="sxs-lookup"><span data-stu-id="45fe4-115">Referenced assemblies</span></span>
  - <span data-ttu-id="45fe4-116">Moduli a cui viene fatto riferimento</span><span class="sxs-lookup"><span data-stu-id="45fe4-116">Referenced modules</span></span>
  - <span data-ttu-id="45fe4-117">Risorse</span><span class="sxs-lookup"><span data-stu-id="45fe4-117">Resources</span></span>
  - <span data-ttu-id="45fe4-118">Il file di chiave con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="45fe4-118">The strong name key file</span></span>
  - <span data-ttu-id="45fe4-119">@ file di risposta</span><span class="sxs-lookup"><span data-stu-id="45fe4-119">@ response files</span></span>
  - <span data-ttu-id="45fe4-120">Analizzatori</span><span class="sxs-lookup"><span data-stu-id="45fe4-120">Analyzers</span></span>
  - <span data-ttu-id="45fe4-121">Set di regole</span><span class="sxs-lookup"><span data-stu-id="45fe4-121">Rulesets</span></span>
  - <span data-ttu-id="45fe4-122">File aggiuntivi che possono essere usati dagli analizzatori</span><span class="sxs-lookup"><span data-stu-id="45fe4-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="45fe4-123">Le impostazioni cultura correnti (per la lingua in cui vengono generati la diagnostica e i messaggi di eccezione).</span><span class="sxs-lookup"><span data-stu-id="45fe4-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="45fe4-124">La codifica predefinita (o la tabella codici corrente) se non è specificata la codifica.</span><span class="sxs-lookup"><span data-stu-id="45fe4-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="45fe4-125">L'esistenza, non esistenza e contenuto dei file nei percorsi di ricerca del compilatore (specificati, ad esempio, da `-lib` o `-recurse`).</span><span class="sxs-lookup"><span data-stu-id="45fe4-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="45fe4-126">La piattaforma CLR in cui viene eseguito il compilatore.</span><span class="sxs-lookup"><span data-stu-id="45fe4-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="45fe4-127">Il valore di `%LIBPATH%`, che può influenzare il caricamento delle dipendenze dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="45fe4-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="45fe4-128">Quando le origini sono disponibili pubblicamente, la compilazione deterministica può essere usata per stabilire se un file binario viene compilato da un'origine attendibile.</span><span class="sxs-lookup"><span data-stu-id="45fe4-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="45fe4-129">Può anche essere utile in un sistema di compilazione continua per determinare se è necessario eseguire le istruzioni di compilazione che dipendono dalle modifiche apportate a un file binario.</span><span class="sxs-lookup"><span data-stu-id="45fe4-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="45fe4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45fe4-130">See also</span></span>

- [<span data-ttu-id="45fe4-131">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45fe4-131">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="45fe4-132">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="45fe4-132">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
