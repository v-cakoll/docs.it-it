---
title: Interfaccia ICorDebugAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 9fb849c78636d5e29f58a70f59aa4cb3cd22df40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784743"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="75f7f-102">Interfaccia ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="75f7f-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="75f7f-103">Fornisce il metodo `Next`, che restituisce un numero specificato di `ICorDebugAppDomainEnum` valori a partire dalla posizione successiva nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="75f7f-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="75f7f-104">Questa interfaccia è una sottoclasse di "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="75f7f-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75f7f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="75f7f-105">Methods</span></span>  
  
|<span data-ttu-id="75f7f-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="75f7f-106">Method</span></span>|<span data-ttu-id="75f7f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f7f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75f7f-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="75f7f-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="75f7f-109">Ottiene il numero specificato di domini applicazione dalla raccolta, a partire dalla posizione corrente del cursore.</span><span class="sxs-lookup"><span data-stu-id="75f7f-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75f7f-110">Note</span><span class="sxs-lookup"><span data-stu-id="75f7f-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75f7f-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="75f7f-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75f7f-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="75f7f-112">Requirements</span></span>  
 <span data-ttu-id="75f7f-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75f7f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75f7f-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75f7f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75f7f-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75f7f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75f7f-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75f7f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f7f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f7f-117">See also</span></span>

- [<span data-ttu-id="75f7f-118">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="75f7f-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="75f7f-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="75f7f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
