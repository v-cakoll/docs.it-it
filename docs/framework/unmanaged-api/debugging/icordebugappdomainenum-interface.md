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
ms.openlocfilehash: 38603fb53b9cd6548595437b05c1e99ef208d940
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895101"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="c6140-102">Interfaccia ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="c6140-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="c6140-103">Fornisce il `Next` metodo, che restituisce un numero specificato di `ICorDebugAppDomainEnum` valori a partire dalla posizione successiva nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c6140-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="c6140-104">Questa interfaccia è una sottoclasse di "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="c6140-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6140-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c6140-105">Methods</span></span>  
  
|<span data-ttu-id="c6140-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c6140-106">Method</span></span>|<span data-ttu-id="c6140-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6140-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6140-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="c6140-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="c6140-109">Ottiene il numero specificato di domini applicazione dalla raccolta, a partire dalla posizione corrente del cursore.</span><span class="sxs-lookup"><span data-stu-id="c6140-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6140-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c6140-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6140-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c6140-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6140-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6140-112">Requirements</span></span>  
 <span data-ttu-id="c6140-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6140-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6140-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6140-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6140-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6140-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6140-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6140-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6140-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6140-117">See also</span></span>

- [<span data-ttu-id="c6140-118">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c6140-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="c6140-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c6140-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
