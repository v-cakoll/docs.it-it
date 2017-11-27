---
title: Metodo ICorDebugStringValue::GetString
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetString
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 077f8488419cee434a8dc8266b0814dfd4196b03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="42ae6-102">Metodo ICorDebugStringValue::GetString</span><span class="sxs-lookup"><span data-stu-id="42ae6-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="42ae6-103">Ottiene la stringa a cui fa riferimento questo oggetto ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="42ae6-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ae6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42ae6-104">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42ae6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="42ae6-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="42ae6-106">[in] Dimensione della matrice `szString`.</span><span class="sxs-lookup"><span data-stu-id="42ae6-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="42ae6-107">[out] Un puntatore al numero di caratteri restituiti nel `szString` matrice.</span><span class="sxs-lookup"><span data-stu-id="42ae6-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="42ae6-108">[out] Matrice che archivia la stringa recuperata.</span><span class="sxs-lookup"><span data-stu-id="42ae6-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ae6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42ae6-109">Requirements</span></span>  
 <span data-ttu-id="42ae6-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42ae6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42ae6-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="42ae6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42ae6-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42ae6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42ae6-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42ae6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
