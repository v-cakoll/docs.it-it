---
title: Metodo ICorDebugAssemblyEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b94ae83f2fb5f71abb8cb3a5c96aac9e268fc5db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405288"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="f9013-102">Metodo ICorDebugAssemblyEnum::Next</span><span class="sxs-lookup"><span data-stu-id="f9013-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="f9013-103">Ottiene il numero di assembly specificato dalla raccolta, a partire dalla posizione corrente del cursore.</span><span class="sxs-lookup"><span data-stu-id="f9013-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9013-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9013-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9013-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9013-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f9013-106">[in] Il numero di assembly da recuperare.</span><span class="sxs-lookup"><span data-stu-id="f9013-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="f9013-107">[out] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugAssembly che rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="f9013-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f9013-108">[out] Puntatore al numero di assembly effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="f9013-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="f9013-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="f9013-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9013-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9013-110">Requirements</span></span>  
 <span data-ttu-id="f9013-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9013-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9013-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f9013-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9013-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f9013-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9013-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9013-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
