---
title: Interfaccia ICorDebugInternalFrame
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
ms.openlocfilehash: 6bc24450cdda2e3ed324256b53b2d137d1eb90e4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788494"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="694b1-102">Interfaccia ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="694b1-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="694b1-103">Rappresenta un frame interno di runtime nello stack.</span><span class="sxs-lookup"><span data-stu-id="694b1-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="694b1-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="694b1-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="694b1-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="694b1-105">Methods</span></span>  
  
|<span data-ttu-id="694b1-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="694b1-106">Method</span></span>|<span data-ttu-id="694b1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="694b1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="694b1-108">Metodo GetFrameType</span><span class="sxs-lookup"><span data-stu-id="694b1-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="694b1-109">Ottiene il tipo del frame interno.</span><span class="sxs-lookup"><span data-stu-id="694b1-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="694b1-110">Note</span><span class="sxs-lookup"><span data-stu-id="694b1-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="694b1-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="694b1-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="694b1-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="694b1-112">Requirements</span></span>  
 <span data-ttu-id="694b1-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="694b1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="694b1-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="694b1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="694b1-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="694b1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="694b1-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="694b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="694b1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="694b1-117">See also</span></span>

- [<span data-ttu-id="694b1-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="694b1-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
