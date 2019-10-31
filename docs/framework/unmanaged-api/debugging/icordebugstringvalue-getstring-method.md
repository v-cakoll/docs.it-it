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
ms.openlocfilehash: c4b01b2c346d3173b2a5ecc144474d7fb1e6dce5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138978"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="ae3e9-102">Metodo ICorDebugStringValue::GetString</span><span class="sxs-lookup"><span data-stu-id="ae3e9-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="ae3e9-103">Ottiene la stringa a cui fa riferimento questo ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="ae3e9-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae3e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae3e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae3e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae3e9-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="ae3e9-106">[in] Dimensione della matrice `szString`.</span><span class="sxs-lookup"><span data-stu-id="ae3e9-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="ae3e9-107">out Puntatore al numero di caratteri restituiti nella matrice `szString`.</span><span class="sxs-lookup"><span data-stu-id="ae3e9-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="ae3e9-108">out Matrice che archivia la stringa recuperata.</span><span class="sxs-lookup"><span data-stu-id="ae3e9-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae3e9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae3e9-109">Requirements</span></span>  
 <span data-ttu-id="ae3e9-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae3e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae3e9-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae3e9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae3e9-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae3e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae3e9-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae3e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
