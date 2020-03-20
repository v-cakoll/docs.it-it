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
ms.openlocfilehash: e23133176cbd703a58c92f9bf1ead530b0bbb8a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178504"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="b0510-102">Metodo ICorDebugStringValue::GetString</span><span class="sxs-lookup"><span data-stu-id="b0510-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="b0510-103">Ottiene la stringa a cui fa riferimento questo ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="b0510-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0510-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0510-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0510-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0510-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="b0510-106">[in] Dimensione della matrice `szString`.</span><span class="sxs-lookup"><span data-stu-id="b0510-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="b0510-107">[fuori] Puntatore al numero di caratteri `szString` restituiti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="b0510-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="b0510-108">[fuori] Matrice in cui viene archiviata la stringa recuperata.</span><span class="sxs-lookup"><span data-stu-id="b0510-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0510-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0510-109">Requirements</span></span>  
 <span data-ttu-id="b0510-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0510-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0510-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0510-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0510-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0510-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0510-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0510-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
