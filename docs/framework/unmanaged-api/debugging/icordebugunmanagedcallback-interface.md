---
title: Interfaccia ICorDebugUnmanagedCallback
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
ms.openlocfilehash: dd5baa282d15d121b62b4dc4dd41bcf9ff393570
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395874"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="6ac15-102">Interfaccia ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="6ac15-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="6ac15-103">Fornisce la notifica di eventi nativi che non sono direttamente correlati all'Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6ac15-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ac15-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6ac15-104">Methods</span></span>  
  
|<span data-ttu-id="6ac15-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6ac15-105">Method</span></span>|<span data-ttu-id="6ac15-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ac15-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ac15-107">Metodo DebugEvent</span><span class="sxs-lookup"><span data-stu-id="6ac15-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="6ac15-108">Notifica al debugger che è stato generato un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="6ac15-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ac15-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="6ac15-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ac15-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6ac15-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ac15-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ac15-111">Requirements</span></span>  
 <span data-ttu-id="6ac15-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ac15-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ac15-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ac15-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ac15-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ac15-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ac15-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ac15-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac15-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6ac15-116">See also</span></span>

- [<span data-ttu-id="6ac15-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6ac15-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
