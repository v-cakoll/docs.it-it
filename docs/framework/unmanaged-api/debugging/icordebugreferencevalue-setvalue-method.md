---
title: Metodo ICorDebugReferenceValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
ms.openlocfilehash: 892471e7b35b4f4093df3f86d4777947b6e484e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378310"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="333d3-102">Metodo ICorDebugReferenceValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="333d3-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="333d3-103">Imposta l'indirizzo di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="333d3-103">Sets the specified memory address.</span></span> <span data-ttu-id="333d3-104">Questo metodo imposta quindi questo ICorDebugReferenceValue in modo che punti a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="333d3-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="333d3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="333d3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="333d3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="333d3-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="333d3-107">in `CORDB_ADDRESS`Valore che specifica l'indirizzo dell'oggetto a cui `ICorDebugReferenceValue` punta.</span><span class="sxs-lookup"><span data-stu-id="333d3-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="333d3-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="333d3-108">Requirements</span></span>  
 <span data-ttu-id="333d3-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="333d3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="333d3-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="333d3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="333d3-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="333d3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="333d3-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="333d3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
