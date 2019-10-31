---
title: Interfaccia ICorDebugCode2
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: 7f0570b668cc33ca509c8522d1ba35ebcfca2453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125580"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="dd6df-102">Interfaccia ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="dd6df-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="dd6df-103">Fornisce metodi che estendono le funzionalità di "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="dd6df-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd6df-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="dd6df-104">Methods</span></span>  
  
|<span data-ttu-id="dd6df-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="dd6df-105">Method</span></span>|<span data-ttu-id="dd6df-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd6df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd6df-107">Metodo GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="dd6df-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="dd6df-108">Ottiene i blocchi di codice di cui questo oggetto di codice è composto.</span><span class="sxs-lookup"><span data-stu-id="dd6df-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="dd6df-109">Metodo GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="dd6df-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="dd6df-110">Ottiene i flag che specificano le condizioni in base alle quali l'oggetto di codice è stato compilato o generato JIT usando il generatore di immagini native (Ngen. exe).</span><span class="sxs-lookup"><span data-stu-id="dd6df-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd6df-111">Note</span><span class="sxs-lookup"><span data-stu-id="dd6df-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd6df-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="dd6df-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd6df-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd6df-113">Requirements</span></span>  
 <span data-ttu-id="dd6df-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd6df-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd6df-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd6df-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd6df-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd6df-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd6df-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd6df-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd6df-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd6df-118">See also</span></span>

- [<span data-ttu-id="dd6df-119">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="dd6df-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="dd6df-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dd6df-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
