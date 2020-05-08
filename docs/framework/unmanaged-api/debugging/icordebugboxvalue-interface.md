---
title: Interfaccia ICorDebugBoxValue
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: bece1be7474c57d38f083e322c2af1b0ba705ee9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894758"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="32e8b-102">Interfaccia ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="32e8b-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="32e8b-103">Sottoclasse di "ICorDebugHeapValue" che rappresenta un oggetto della classe di valori boxed.</span><span class="sxs-lookup"><span data-stu-id="32e8b-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="32e8b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="32e8b-104">Methods</span></span>  
  
|<span data-ttu-id="32e8b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="32e8b-105">Method</span></span>|<span data-ttu-id="32e8b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32e8b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="32e8b-107">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="32e8b-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="32e8b-108">Ottiene un puntatore a interfaccia per l'istanza "ICorDebugObjectValue" boxed.</span><span class="sxs-lookup"><span data-stu-id="32e8b-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32e8b-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="32e8b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32e8b-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="32e8b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e8b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32e8b-111">Requirements</span></span>  
 <span data-ttu-id="32e8b-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32e8b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e8b-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32e8b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32e8b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32e8b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32e8b-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e8b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e8b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32e8b-116">See also</span></span>

- [<span data-ttu-id="32e8b-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="32e8b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
