---
title: Strutture di profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 229218cb15963846da91f688b0d2faacb20031c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000441"
---
# <a name="profiling-structures"></a><span data-ttu-id="50d69-102">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="50d69-102">Profiling Structures</span></span>
<span data-ttu-id="50d69-103">Questa sezione descrive le strutture non gestite usate dall'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="50d69-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50d69-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="50d69-104">In This Section</span></span>  
 [<span data-ttu-id="50d69-105">Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="50d69-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="50d69-106">Fornisce a Common Language Runtime le informazioni su un assembly di riferimento che deve considerare quando esegue un percorso di chiusura del riferimento ad assembly.</span><span class="sxs-lookup"><span data-stu-id="50d69-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="50d69-107">Struttura COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="50d69-107">COR_PRF_CODE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)  
 <span data-ttu-id="50d69-108">Rappresenta un blocco contiguo di codice nativo archiviato in memoria.</span><span class="sxs-lookup"><span data-stu-id="50d69-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="50d69-109">Struttura COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="50d69-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="50d69-110">Archivia le informazioni su un'istanza di una clausola di eccezione specifica e il relativo frame associato.</span><span class="sxs-lookup"><span data-stu-id="50d69-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="50d69-111">Struttura COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="50d69-111">COR_PRF_FUNCTION Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-structure.md)  
 <span data-ttu-id="50d69-112">Fornisce una rappresentazione univoca di una funzione combinando il relativo ID con l'ID della versione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="50d69-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="50d69-113">Struttura COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="50d69-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="50d69-114">Rappresenta gli argomenti di una funzione, in ordine da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="50d69-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="50d69-115">Struttura COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="50d69-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="50d69-116">Rappresenta un blocco di argomenti della funzione archiviati in modo contiguo da sinistra a destra in memoria.</span><span class="sxs-lookup"><span data-stu-id="50d69-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="50d69-117">Struttura COR_PRF_GC_GENERATION_RANGE</span><span class="sxs-lookup"><span data-stu-id="50d69-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="50d69-118">Descrive un intervallo, ovvero un blocco, di memoria sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="50d69-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="50d69-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="50d69-119">Related Sections</span></span>  
 <span data-ttu-id="50d69-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="50d69-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="50d69-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="50d69-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="50d69-122">Panoramica della profilatura</span><span class="sxs-lookup"><span data-stu-id="50d69-122">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="50d69-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="50d69-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="50d69-124">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="50d69-124">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="50d69-125">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="50d69-125">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
