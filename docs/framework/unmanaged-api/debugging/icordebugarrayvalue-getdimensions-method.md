---
title: Metodo ICorDebugArrayValue::GetDimensions
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: c5199794098e4d83588728eeb165aee5f81fe4c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088505"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="f19eb-102">Metodo ICorDebugArrayValue::GetDimensions</span><span class="sxs-lookup"><span data-stu-id="f19eb-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="f19eb-103">Ottiene il numero di elementi in ogni dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="f19eb-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f19eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f19eb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f19eb-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="f19eb-106">in Numero di dimensioni di questo oggetto ICorDebugArrayValue.</span><span class="sxs-lookup"><span data-stu-id="f19eb-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="f19eb-107">Questo valore corrisponde anche alla dimensione della matrice `dims` perché la relativa dimensione è uguale al numero di dimensioni dell'oggetto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="f19eb-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="f19eb-108">out Matrice di Integer, ognuno dei quali specifica il numero di elementi in una dimensione in questo oggetto `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="f19eb-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f19eb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f19eb-109">Requirements</span></span>  
 <span data-ttu-id="f19eb-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f19eb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f19eb-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f19eb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f19eb-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f19eb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f19eb-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f19eb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
