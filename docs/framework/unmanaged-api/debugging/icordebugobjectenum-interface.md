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
ms.openlocfilehash: 0526c050bcf1316eccf2c756a404fbb971e6d7d0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792733"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="cd61f-102">Interfaccia ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="cd61f-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="cd61f-103">Implementa i metodi ICorDebugEnum ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA).</span><span class="sxs-lookup"><span data-stu-id="cd61f-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd61f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cd61f-104">Methods</span></span>  
  
|<span data-ttu-id="cd61f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cd61f-105">Method</span></span>|<span data-ttu-id="cd61f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd61f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd61f-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="cd61f-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="cd61f-108">Ottiene l'RVA del numero specificato di oggetti dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="cd61f-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd61f-109">Note</span><span class="sxs-lookup"><span data-stu-id="cd61f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd61f-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="cd61f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd61f-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="cd61f-111">Requirements</span></span>  
 <span data-ttu-id="cd61f-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd61f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd61f-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd61f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd61f-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd61f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd61f-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd61f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd61f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd61f-116">See also</span></span>

- [<span data-ttu-id="cd61f-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd61f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
