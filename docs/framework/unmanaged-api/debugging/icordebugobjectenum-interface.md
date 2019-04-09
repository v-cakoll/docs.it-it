---
title: Interfaccia ICorDebugObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0144539987f14bed83bfc9eab2f5ca26d2a609ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157771"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="f2517-102">Interfaccia ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="f2517-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="f2517-103">Implementa i metodi ICorDebugEnum ed enumera le matrici di oggetti dai rispettivi indirizzi virtuali relativi (RVA).</span><span class="sxs-lookup"><span data-stu-id="f2517-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2517-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f2517-104">Methods</span></span>  
  
|<span data-ttu-id="f2517-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f2517-105">Method</span></span>|<span data-ttu-id="f2517-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2517-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2517-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="f2517-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="f2517-108">Ottiene il RVA del numero specificato di oggetti dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="f2517-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2517-109">Note</span><span class="sxs-lookup"><span data-stu-id="f2517-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2517-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f2517-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2517-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2517-111">Requirements</span></span>  
 <span data-ttu-id="f2517-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2517-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2517-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2517-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2517-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2517-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f2517-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f2517-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2517-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2517-116">See also</span></span>

- [<span data-ttu-id="f2517-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f2517-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
