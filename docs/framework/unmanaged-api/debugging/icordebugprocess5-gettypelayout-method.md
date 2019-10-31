---
title: Metodo ICorDebugProcess5::GetTypeLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: a348c3b2ad33a5d68b1bc46e9a284f2d2a9c7304
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121290"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="23abd-102">Metodo ICorDebugProcess5::GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="23abd-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="23abd-103">Ottiene informazioni sul layout di un oggetto in memoria in base al relativo identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="23abd-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23abd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23abd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23abd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="23abd-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="23abd-106">in Token [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) che specifica il tipo di cui si desidera il layout.</span><span class="sxs-lookup"><span data-stu-id="23abd-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="23abd-107">out Puntatore a una struttura [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) che contiene informazioni sul layout dell'oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="23abd-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23abd-108">Note</span><span class="sxs-lookup"><span data-stu-id="23abd-108">Remarks</span></span>  
 <span data-ttu-id="23abd-109">Il metodo `ICorDebugProcess5::GetTypeLayout` fornisce informazioni su un oggetto in base al relativo [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), restituito da diversi altri metodi [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="23abd-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="23abd-110">Le informazioni vengono fornite da una struttura [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) popolata dal metodo.</span><span class="sxs-lookup"><span data-stu-id="23abd-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23abd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23abd-111">Requirements</span></span>  
 <span data-ttu-id="23abd-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23abd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23abd-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23abd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23abd-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23abd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23abd-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23abd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23abd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23abd-116">See also</span></span>

- [<span data-ttu-id="23abd-117">Struttura COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="23abd-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [<span data-ttu-id="23abd-118">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="23abd-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="23abd-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="23abd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
