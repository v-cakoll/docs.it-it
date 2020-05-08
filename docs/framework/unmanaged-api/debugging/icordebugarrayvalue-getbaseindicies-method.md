---
title: Metodo ICorDebugArrayValue::GetBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: 9aadbe7c6f18c6b15350267d1f9ecaa3a23cdd20
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895075"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="82e24-102">Metodo ICorDebugArrayValue::GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="82e24-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="82e24-103">Ottiene l'indice di base di ogni dimensione nella matrice.</span><span class="sxs-lookup"><span data-stu-id="82e24-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e24-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82e24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82e24-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82e24-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="82e24-106">in Numero di dimensioni dell' `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="82e24-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="82e24-107">Questo valore corrisponde anche alla dimensione della `indicies` matrice perché la relativa dimensione è uguale al numero di dimensioni dell' `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="82e24-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="82e24-108">out Matrice di Integer, ognuno dei quali è l'indice di base, ovvero l'indice iniziale, di una dimensione di questo `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="82e24-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82e24-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82e24-109">Requirements</span></span>  
 <span data-ttu-id="82e24-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82e24-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82e24-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82e24-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82e24-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82e24-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82e24-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82e24-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
