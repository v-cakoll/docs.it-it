---
title: Interfaccia ICorDebugExceptionObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6805b7b49f76b80161aef5051fe3c284192f582
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413774"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="4ec3d-102">Interfaccia ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="4ec3d-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="4ec3d-103">Estende l'interfaccia "ICorDebugObjectValue" per fornire informazioni sull'analisi dello stack da un oggetto eccezione gestito.</span><span class="sxs-lookup"><span data-stu-id="4ec3d-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ec3d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4ec3d-104">Methods</span></span>  
  
|<span data-ttu-id="4ec3d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4ec3d-105">Method</span></span>|<span data-ttu-id="4ec3d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ec3d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ec3d-107">Metodo EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="4ec3d-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="4ec3d-108">Ottiene un enumeratore per lo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="4ec3d-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ec3d-109">Note</span><span class="sxs-lookup"><span data-stu-id="4ec3d-109">Remarks</span></span>  
 <span data-ttu-id="4ec3d-110">La chiamata a `QueryInterface` avrà esito positivo per gli oggetti gestiti che derivano da <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ec3d-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ec3d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ec3d-111">Requirements</span></span>  
 <span data-ttu-id="4ec3d-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ec3d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ec3d-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4ec3d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ec3d-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4ec3d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ec3d-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ec3d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec3d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ec3d-116">See Also</span></span>  
 [<span data-ttu-id="4ec3d-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4ec3d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4ec3d-118">Debug</span><span class="sxs-lookup"><span data-stu-id="4ec3d-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
