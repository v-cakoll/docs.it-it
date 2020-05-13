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
ms.openlocfilehash: 332bc99795c0a4c896b60c61941a5a24b3f4accc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209942"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="76316-102">Interfaccia ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="76316-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="76316-103">Rappresenta un frame interno di runtime nello stack.</span><span class="sxs-lookup"><span data-stu-id="76316-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="76316-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="76316-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76316-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="76316-105">Methods</span></span>  
  
|<span data-ttu-id="76316-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="76316-106">Method</span></span>|<span data-ttu-id="76316-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76316-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76316-108">Metodo GetFrameType</span><span class="sxs-lookup"><span data-stu-id="76316-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="76316-109">Ottiene il tipo del frame interno.</span><span class="sxs-lookup"><span data-stu-id="76316-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76316-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="76316-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76316-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="76316-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76316-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76316-112">Requirements</span></span>  
 <span data-ttu-id="76316-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76316-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76316-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76316-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76316-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76316-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76316-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76316-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76316-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76316-117">See also</span></span>

- [<span data-ttu-id="76316-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="76316-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
