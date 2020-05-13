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
ms.openlocfilehash: 0594caf53a889d51ea78e2ee9d6fff4d30f7cff2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205283"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="27513-102">Interfaccia ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="27513-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="27513-103">Implementa i metodi ICorDebugEnum ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA).</span><span class="sxs-lookup"><span data-stu-id="27513-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27513-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="27513-104">Methods</span></span>  
  
|<span data-ttu-id="27513-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="27513-105">Method</span></span>|<span data-ttu-id="27513-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27513-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27513-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="27513-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="27513-108">Ottiene l'RVA del numero specificato di oggetti dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="27513-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27513-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="27513-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27513-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="27513-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27513-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27513-111">Requirements</span></span>  
 <span data-ttu-id="27513-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27513-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27513-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27513-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27513-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27513-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27513-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27513-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27513-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27513-116">See also</span></span>

- [<span data-ttu-id="27513-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="27513-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
