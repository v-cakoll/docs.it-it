---
title: -deterministic
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
ms.openlocfilehash: 9b611a72656bdd570eccec8a0585bf5ce6fa55f6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716797"
---
# <a name="-deterministic"></a><span data-ttu-id="ff33a-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="ff33a-102">-deterministic</span></span>

<span data-ttu-id="ff33a-103">Fa sì che il compilatore generi un assembly il cui output byte per byte è identico in tutte le compilazioni se si usano input identici.</span><span class="sxs-lookup"><span data-stu-id="ff33a-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="ff33a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff33a-104">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="ff33a-105">Note</span><span class="sxs-lookup"><span data-stu-id="ff33a-105">Remarks</span></span>

<span data-ttu-id="ff33a-106">Per impostazione predefinita, l'output del compilatore che deriva da un determinato set di input è univoco, poiché il compilatore aggiunge un timestamp e un GUID generato da numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="ff33a-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="ff33a-107">L'opzione `-deterministic` si usa per generare un *assembly deterministico* il cui contenuto binario è identico in tutte le compilazioni purché l'input rimanga lo stesso.</span><span class="sxs-lookup"><span data-stu-id="ff33a-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="ff33a-108">Il compilatore considera i seguenti input al fine del determinismo:</span><span class="sxs-lookup"><span data-stu-id="ff33a-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="ff33a-109">La sequenza dei parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ff33a-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="ff33a-110">Il contenuto del file di risposta del file RSP del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ff33a-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="ff33a-111">La versione precisa del compilatore in uso e i relativi assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ff33a-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="ff33a-112">Il percorso della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="ff33a-112">The current directory path.</span></span>
- <span data-ttu-id="ff33a-113">Il contenuto binario di tutti i file passati in modo esplicito al compilatore direttamente o indirettamente, tra cui:</span><span class="sxs-lookup"><span data-stu-id="ff33a-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="ff33a-114">File di origine</span><span class="sxs-lookup"><span data-stu-id="ff33a-114">Source files</span></span>
  - <span data-ttu-id="ff33a-115">Assembly a cui viene fatto riferimento</span><span class="sxs-lookup"><span data-stu-id="ff33a-115">Referenced assemblies</span></span>
  - <span data-ttu-id="ff33a-116">Moduli a cui viene fatto riferimento</span><span class="sxs-lookup"><span data-stu-id="ff33a-116">Referenced modules</span></span>
  - <span data-ttu-id="ff33a-117">Risorse</span><span class="sxs-lookup"><span data-stu-id="ff33a-117">Resources</span></span>
  - <span data-ttu-id="ff33a-118">Il file di chiave con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="ff33a-118">The strong name key file</span></span>
  - <span data-ttu-id="ff33a-119">@ file di risposta</span><span class="sxs-lookup"><span data-stu-id="ff33a-119">@ response files</span></span>
  - <span data-ttu-id="ff33a-120">Analizzatori</span><span class="sxs-lookup"><span data-stu-id="ff33a-120">Analyzers</span></span>
  - <span data-ttu-id="ff33a-121">Set di regole</span><span class="sxs-lookup"><span data-stu-id="ff33a-121">Rulesets</span></span>
  - <span data-ttu-id="ff33a-122">File aggiuntivi che possono essere usati dagli analizzatori</span><span class="sxs-lookup"><span data-stu-id="ff33a-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="ff33a-123">Le impostazioni cultura correnti (per la lingua in cui vengono generati la diagnostica e i messaggi di eccezione).</span><span class="sxs-lookup"><span data-stu-id="ff33a-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="ff33a-124">La codifica predefinita (o la tabella codici corrente) se non è specificata la codifica.</span><span class="sxs-lookup"><span data-stu-id="ff33a-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="ff33a-125">L'esistenza, non esistenza e contenuto dei file nei percorsi di ricerca del compilatore (specificati, ad esempio, da `-lib` o `-recurse`).</span><span class="sxs-lookup"><span data-stu-id="ff33a-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="ff33a-126">La piattaforma CLR in cui viene eseguito il compilatore.</span><span class="sxs-lookup"><span data-stu-id="ff33a-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="ff33a-127">Il valore di `%LIBPATH%`, che può influenzare il caricamento delle dipendenze dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="ff33a-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="ff33a-128">Quando le origini sono disponibili pubblicamente, la compilazione deterministica può essere usata per stabilire se un file binario viene compilato da un'origine attendibile.</span><span class="sxs-lookup"><span data-stu-id="ff33a-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="ff33a-129">Può anche essere utile in un sistema di compilazione continua per determinare se è necessario eseguire le istruzioni di compilazione che dipendono dalle modifiche apportate a un file binario.</span><span class="sxs-lookup"><span data-stu-id="ff33a-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff33a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff33a-130">See also</span></span>

- [<span data-ttu-id="ff33a-131">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff33a-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ff33a-132">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="ff33a-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
