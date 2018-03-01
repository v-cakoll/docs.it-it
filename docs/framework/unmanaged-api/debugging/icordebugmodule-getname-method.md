---
title: Metodo ICorDebugModule::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64be936277b0ebe04248ae2913a882b628ee363f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="a3928-102">Metodo ICorDebugModule::GetName</span><span class="sxs-lookup"><span data-stu-id="a3928-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="a3928-103">Ottiene il nome del file del modulo.</span><span class="sxs-lookup"><span data-stu-id="a3928-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3928-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3928-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3928-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3928-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="a3928-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="a3928-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a3928-107">[in] Puntatore alla lunghezza del nome restituito.</span><span class="sxs-lookup"><span data-stu-id="a3928-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="a3928-108">[out] Matrice che archivia il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="a3928-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3928-109">Note</span><span class="sxs-lookup"><span data-stu-id="a3928-109">Remarks</span></span>  
 <span data-ttu-id="a3928-110">Il `GetName` metodo restituisce un HRESULT S_OK se il nome di file del modulo corrisponde al nome sul disco.</span><span class="sxs-lookup"><span data-stu-id="a3928-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="a3928-111">`GetName`Restituisce un HRESULT di S_FALSE se il nome viene creato, ad esempio per un modulo dinamico o in memoria.</span><span class="sxs-lookup"><span data-stu-id="a3928-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3928-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3928-112">Requirements</span></span>  
 <span data-ttu-id="a3928-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3928-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3928-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a3928-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3928-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3928-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3928-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3928-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3928-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3928-117">See Also</span></span>  
    
 
