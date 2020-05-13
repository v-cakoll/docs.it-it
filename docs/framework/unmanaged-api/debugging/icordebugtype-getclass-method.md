---
title: Metodo ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 878a57514af34730049864f17f4853c1237904c2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379965"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="663e7-102">Metodo ICorDebugType::GetClass</span><span class="sxs-lookup"><span data-stu-id="663e7-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="663e7-103">Ottiene un puntatore a interfaccia a un ICorDebugClass che rappresenta il tipo generico di cui non è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="663e7-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="663e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="663e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="663e7-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="663e7-106">out Puntatore all'indirizzo di un' `ICorDebugClass` interfaccia che rappresenta il tipo generico di cui non è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="663e7-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="663e7-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="663e7-107">Remarks</span></span>  
 <span data-ttu-id="663e7-108">`GetClass`può essere chiamato solo in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="663e7-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="663e7-109">Chiamare [ICorDebugType:: GetType](icordebugtype-gettype-method.md) prima di chiamare `GetClass` .</span><span class="sxs-lookup"><span data-stu-id="663e7-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="663e7-110">Se `ICorDebugType::GetType` restituisce un valore CorElementType ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` può essere chiamato per ottenere il tipo di cui non è stata creata un'istanza per un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="663e7-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="663e7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="663e7-111">Requirements</span></span>  
 <span data-ttu-id="663e7-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="663e7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="663e7-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="663e7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="663e7-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="663e7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="663e7-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="663e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
