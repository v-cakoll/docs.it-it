---
title: Strutture di profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: c3bbc66079e05abf494ad112b8aa0ac68e3c3e2f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868109"
---
# <a name="profiling-structures"></a><span data-ttu-id="734d5-102">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="734d5-102">Profiling Structures</span></span>
<span data-ttu-id="734d5-103">Questa sezione descrive le strutture non gestite usate dall'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="734d5-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="734d5-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="734d5-104">In This Section</span></span>  
 [<span data-ttu-id="734d5-105">Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="734d5-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="734d5-106">Fornisce a Common Language Runtime le informazioni su un assembly di riferimento che deve considerare quando esegue un percorso di chiusura del riferimento ad assembly.</span><span class="sxs-lookup"><span data-stu-id="734d5-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="734d5-107">Struttura COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="734d5-107">COR_PRF_CODE_INFO Structure</span></span>](cor-prf-code-info-structure.md)  
 <span data-ttu-id="734d5-108">Rappresenta un blocco contiguo di codice nativo archiviato in memoria.</span><span class="sxs-lookup"><span data-stu-id="734d5-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="734d5-109">Struttura COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="734d5-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="734d5-110">Archivia le informazioni su un'istanza di una clausola di eccezione specifica e il relativo frame associato.</span><span class="sxs-lookup"><span data-stu-id="734d5-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="734d5-111">Struttura COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="734d5-111">COR_PRF_FUNCTION Structure</span></span>](cor-prf-function-structure.md)  
 <span data-ttu-id="734d5-112">Fornisce una rappresentazione univoca di una funzione combinando il relativo ID con l'ID della versione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="734d5-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="734d5-113">Struttura COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="734d5-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="734d5-114">Rappresenta gli argomenti di una funzione, in ordine da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="734d5-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="734d5-115">Struttura COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="734d5-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="734d5-116">Rappresenta un blocco di argomenti della funzione archiviati in modo contiguo da sinistra a destra in memoria.</span><span class="sxs-lookup"><span data-stu-id="734d5-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="734d5-117">Struttura COR_PRF_GC_GENERATION_RANGE</span><span class="sxs-lookup"><span data-stu-id="734d5-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="734d5-118">Descrive un intervallo, ovvero un blocco, di memoria sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="734d5-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="734d5-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="734d5-119">Related Sections</span></span>  
 <span data-ttu-id="734d5-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="734d5-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="734d5-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="734d5-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="734d5-122">Panoramica della profilatura</span><span class="sxs-lookup"><span data-stu-id="734d5-122">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="734d5-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="734d5-123">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="734d5-124">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="734d5-124">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="734d5-125">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="734d5-125">Profiling Enumerations</span></span>](profiling-enumerations.md)
