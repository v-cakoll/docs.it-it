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
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791302"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="ecc6b-102">Metodo ICorDebugType::GetClass</span><span class="sxs-lookup"><span data-stu-id="ecc6b-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="ecc6b-103">Ottiene un puntatore a interfaccia a un ICorDebugClass che rappresenta il tipo generico di cui non è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="ecc6b-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecc6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecc6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ecc6b-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="ecc6b-106">out Puntatore all'indirizzo di un'interfaccia `ICorDebugClass` che rappresenta il tipo generico privo di istanze.</span><span class="sxs-lookup"><span data-stu-id="ecc6b-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc6b-107">Note</span><span class="sxs-lookup"><span data-stu-id="ecc6b-107">Remarks</span></span>  
 <span data-ttu-id="ecc6b-108">`GetClass` può essere chiamato solo in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="ecc6b-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="ecc6b-109">Chiamare [ICorDebugType:: GetType](icordebugtype-gettype-method.md) prima di chiamare `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="ecc6b-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="ecc6b-110">Se `ICorDebugType::GetType` restituisce un valore CorElementType ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` può essere chiamato per ottenere il tipo di cui non è stata creata un'istanza per un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="ecc6b-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc6b-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ecc6b-111">Requirements</span></span>  
 <span data-ttu-id="ecc6b-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecc6b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecc6b-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecc6b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecc6b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecc6b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecc6b-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecc6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
