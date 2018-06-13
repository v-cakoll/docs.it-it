---
title: Metodo ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdfcd45b15ddc1491b12de0fa42901b6d3f7fe9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413153"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="731d2-102">Metodo ICorDebugCode2::GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="731d2-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="731d2-103">Ottiene i blocchi di codice che è costituito da questo oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="731d2-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="731d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="731d2-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="731d2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="731d2-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="731d2-106">[in] Dimensioni di `chunks` matrice.</span><span class="sxs-lookup"><span data-stu-id="731d2-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="731d2-107">[out] Il numero di blocchi restituiti nella `chunks` matrice.</span><span class="sxs-lookup"><span data-stu-id="731d2-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="731d2-108">[out] Matrice di strutture "CodeChunkInfo", ognuno dei quali rappresenta un singolo blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="731d2-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="731d2-109">Se il valore di `cbufSize` è 0, questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="731d2-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="731d2-110">Note</span><span class="sxs-lookup"><span data-stu-id="731d2-110">Remarks</span></span>  
 <span data-ttu-id="731d2-111">I blocchi di codice si sovrapporranno mai e seguiranno l'ordine in cui sarebbero stati concatenati da [ICorDebugCode:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="731d2-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="731d2-112">Un oggetto di codice Microsoft intermediate language (MSIL) in .NET Framework versione 2.0 includerà un solo blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="731d2-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="731d2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="731d2-113">Requirements</span></span>  
 <span data-ttu-id="731d2-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="731d2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="731d2-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="731d2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="731d2-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="731d2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="731d2-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="731d2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731d2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="731d2-118">See Also</span></span>  
 
