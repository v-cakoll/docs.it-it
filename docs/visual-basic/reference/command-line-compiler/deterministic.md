---
title: -deterministica
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a><span data-ttu-id="6a2a5-102">-deterministica</span><span class="sxs-lookup"><span data-stu-id="6a2a5-102">-deterministic</span></span>

<span data-ttu-id="6a2a5-103">Fa sì che il compilatore genera un assembly il cui output di byte per byte è identico per le compilazioni per gli input identiche.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="6a2a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a2a5-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="6a2a5-105">Note</span><span class="sxs-lookup"><span data-stu-id="6a2a5-105">Remarks</span></span>

<span data-ttu-id="6a2a5-106">Per impostazione predefinita, l'output del compilatore da un set specificato di input sia univoco, poiché il compilatore aggiunge un timestamp e un GUID generato da numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="6a2a5-107">Utilizzare la `-deterministic` opzione per generare un *assembly deterministica*, uno cui contenuto binario è identica tra compilazioni, purché l'input rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="6a2a5-108">Il compilatore considera i seguenti input allo scopo di determinismo:</span><span class="sxs-lookup"><span data-stu-id="6a2a5-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="6a2a5-109">La sequenza di parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="6a2a5-110">Il contenuto del file di risposta del compilatore rsp.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="6a2a5-111">La versione precisa usata dal compilatore e il relativo assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="6a2a5-112">Il percorso della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-112">The current directory path.</span></span>
- <span data-ttu-id="6a2a5-113">Il contenuto binario di tutti i file in modo esplicito passato al compilatore direttamente o indirettamente, tra cui:</span><span class="sxs-lookup"><span data-stu-id="6a2a5-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span> 
    - <span data-ttu-id="6a2a5-114">File di origine</span><span class="sxs-lookup"><span data-stu-id="6a2a5-114">Source files</span></span>
    - <span data-ttu-id="6a2a5-115">assembly di riferimento</span><span class="sxs-lookup"><span data-stu-id="6a2a5-115">Referenced assemblies</span></span>
    - <span data-ttu-id="6a2a5-116">Moduli di cui viene fatto riferimento</span><span class="sxs-lookup"><span data-stu-id="6a2a5-116">Referenced modules</span></span>
    - <span data-ttu-id="6a2a5-117">Risorse</span><span class="sxs-lookup"><span data-stu-id="6a2a5-117">Resources</span></span>
    - <span data-ttu-id="6a2a5-118">Il file di chiave con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="6a2a5-118">The strong name key file</span></span>
    - <span data-ttu-id="6a2a5-119">@ file di risposta</span><span class="sxs-lookup"><span data-stu-id="6a2a5-119">@ response files</span></span>
    - <span data-ttu-id="6a2a5-120">Analizzatori</span><span class="sxs-lookup"><span data-stu-id="6a2a5-120">Analyzers</span></span>
    - <span data-ttu-id="6a2a5-121">Set di regole</span><span class="sxs-lookup"><span data-stu-id="6a2a5-121">Rulesets</span></span>
    - <span data-ttu-id="6a2a5-122">File aggiuntivi che possono essere usati dagli analizzatori</span><span class="sxs-lookup"><span data-stu-id="6a2a5-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="6a2a5-123">Le impostazioni cultura correnti (per la lingua in cui la diagnostica e l'eccezione vengono generati messaggi).</span><span class="sxs-lookup"><span data-stu-id="6a2a5-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="6a2a5-124">La codifica predefinita (o la tabella codici corrente) se non è specificata la codifica.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="6a2a5-125">L'esistenza non esistenza e contenuto dei file nei percorsi di ricerca del compilatore (specificato, ad esempio, tramite `/lib` o `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="6a2a5-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="6a2a5-126">La piattaforma CLR in cui viene eseguito il compilatore.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="6a2a5-127">Il valore di `%LIBPATH%`, che possono influenzare il caricamento di dipendenza analyzer.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="6a2a5-128">Quando le origini sono disponibile pubblicamente, compilazione deterministica può essere utilizzata per stabilire se un file binario viene compilato da una fonte attendibile.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="6a2a5-129">Può anche essere utile in un sistema di compilazione continua per determinare se è necessario eseguire le istruzioni di compilazione che dipendono dalle modifiche apportate a un file binario.</span><span class="sxs-lookup"><span data-stu-id="6a2a5-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="6a2a5-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a2a5-130">See Also</span></span>
[<span data-ttu-id="6a2a5-131">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a2a5-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
[<span data-ttu-id="6a2a5-132">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="6a2a5-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
