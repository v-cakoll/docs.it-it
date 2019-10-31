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
ms.openlocfilehash: a5762079861f04e1869b206c3200c3a024c1b77a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091003"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="aca61-102">Interfaccia ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="aca61-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="aca61-103">Estende l'interfaccia "ICorDebugObjectValue" per fornire informazioni di analisi dello stack da un oggetto eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="aca61-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aca61-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="aca61-104">Methods</span></span>  
  
|<span data-ttu-id="aca61-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="aca61-105">Method</span></span>|<span data-ttu-id="aca61-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aca61-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aca61-107">Metodo EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="aca61-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="aca61-108">Ottiene un enumeratore per lo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="aca61-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aca61-109">Note</span><span class="sxs-lookup"><span data-stu-id="aca61-109">Remarks</span></span>  
 <span data-ttu-id="aca61-110">La chiamata a `QueryInterface` avrà esito positivo per gli oggetti gestiti che derivano da <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aca61-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aca61-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aca61-111">Requirements</span></span>  
 <span data-ttu-id="aca61-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aca61-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca61-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aca61-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aca61-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aca61-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aca61-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca61-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca61-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aca61-116">See also</span></span>

- [<span data-ttu-id="aca61-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="aca61-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="aca61-118">Debug</span><span class="sxs-lookup"><span data-stu-id="aca61-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
