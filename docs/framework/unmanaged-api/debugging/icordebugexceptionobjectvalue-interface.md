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
ms.openlocfilehash: 8e4f745440936a39e22faf60d10a05a0bb110606
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975953"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="1ad45-102">Interfaccia ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="1ad45-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="1ad45-103">Estende l'interfaccia "ICorDebugObjectValue" per fornire informazioni di analisi dello stack da un oggetto eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="1ad45-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ad45-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1ad45-104">Methods</span></span>  
  
|<span data-ttu-id="1ad45-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1ad45-105">Method</span></span>|<span data-ttu-id="1ad45-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ad45-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ad45-107">Metodo EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="1ad45-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="1ad45-108">Ottiene un enumeratore per lo stack di chiamate incorporato in un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="1ad45-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ad45-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1ad45-109">Remarks</span></span>  
 <span data-ttu-id="1ad45-110">La chiamata a `QueryInterface` avrà esito positivo per gli oggetti gestiti che <xref:System.Exception?displayProperty=nameWithType>derivano da.</span><span class="sxs-lookup"><span data-stu-id="1ad45-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ad45-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ad45-111">Requirements</span></span>  
 <span data-ttu-id="1ad45-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ad45-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ad45-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ad45-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ad45-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ad45-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ad45-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ad45-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad45-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ad45-116">See also</span></span>

- [<span data-ttu-id="1ad45-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1ad45-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1ad45-118">Debug</span><span class="sxs-lookup"><span data-stu-id="1ad45-118">Debugging</span></span>](index.md)
