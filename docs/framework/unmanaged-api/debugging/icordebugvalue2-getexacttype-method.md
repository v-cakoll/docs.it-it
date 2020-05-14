---
title: Metodo ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: dcec97bac2aefc8db1f9351f1dacb0f36fc0d2a0
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396803"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="b0121-102">Metodo ICorDebugValue2::GetExactType</span><span class="sxs-lookup"><span data-stu-id="b0121-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="b0121-103">Ottiene un puntatore a interfaccia a un oggetto "ICorDebugType" che rappresenta l'oggetto <xref:System.Type> di questo valore.</span><span class="sxs-lookup"><span data-stu-id="b0121-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0121-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0121-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0121-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0121-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="b0121-106">out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta l' <xref:System.Type> oggetto del valore rappresentato da questo oggetto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="b0121-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0121-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="b0121-107">Remarks</span></span>  
 <span data-ttu-id="b0121-108">Il metodo in grado di riconoscere i generics `GetExactType` sostituisce entrambi i metodi [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) e [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , ciascuno dei quali restituisce informazioni sul tipo di un valore.</span><span class="sxs-lookup"><span data-stu-id="b0121-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0121-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0121-109">Requirements</span></span>  
 <span data-ttu-id="b0121-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0121-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0121-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0121-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0121-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0121-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0121-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0121-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0121-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0121-114">See also</span></span>
