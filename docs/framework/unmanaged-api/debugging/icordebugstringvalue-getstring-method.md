---
title: Metodo ICorDebugStringValue::GetString
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77c88786befb92960f4cfa4a960cbfc624318b26
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771600"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="a13aa-102">Metodo ICorDebugStringValue::GetString</span><span class="sxs-lookup"><span data-stu-id="a13aa-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="a13aa-103">Ottiene la stringa di cui fa riferimento ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="a13aa-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a13aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a13aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a13aa-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="a13aa-106">[in] Dimensione della matrice `szString`.</span><span class="sxs-lookup"><span data-stu-id="a13aa-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="a13aa-107">[out] Un puntatore al numero di caratteri restituiti nella `szString` matrice.</span><span class="sxs-lookup"><span data-stu-id="a13aa-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="a13aa-108">[out] Matrice che archivia la stringa recuperata.</span><span class="sxs-lookup"><span data-stu-id="a13aa-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13aa-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a13aa-109">Requirements</span></span>  
 <span data-ttu-id="a13aa-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a13aa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13aa-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a13aa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a13aa-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a13aa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a13aa-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13aa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
