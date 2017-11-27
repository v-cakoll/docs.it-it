---
title: Metodo ICorDebugModule::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b10e0eed3c2df8781aa7085cc43157894cc6e2c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="62689-102">Metodo ICorDebugModule::GetName</span><span class="sxs-lookup"><span data-stu-id="62689-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="62689-103">Ottiene il nome del file del modulo.</span><span class="sxs-lookup"><span data-stu-id="62689-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62689-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62689-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62689-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62689-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="62689-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="62689-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="62689-107">[in] Puntatore alla lunghezza del nome restituito.</span><span class="sxs-lookup"><span data-stu-id="62689-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="62689-108">[out] Matrice che archivia il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="62689-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62689-109">Note</span><span class="sxs-lookup"><span data-stu-id="62689-109">Remarks</span></span>  
 <span data-ttu-id="62689-110">Il `GetName` metodo restituisce un HRESULT S_OK se il nome di file del modulo corrisponde al nome sul disco.</span><span class="sxs-lookup"><span data-stu-id="62689-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="62689-111">`GetName`Restituisce un HRESULT di S_FALSE se il nome viene creato, ad esempio per un modulo dinamico o in memoria.</span><span class="sxs-lookup"><span data-stu-id="62689-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62689-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62689-112">Requirements</span></span>  
 <span data-ttu-id="62689-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62689-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62689-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="62689-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62689-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62689-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62689-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62689-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62689-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62689-117">See Also</span></span>  
    
 
