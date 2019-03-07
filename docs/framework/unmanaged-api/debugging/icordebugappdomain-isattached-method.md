---
title: Metodo ICorDebugAppDomain::IsAttached
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa9576f568ef1f6da3eef812abb9674aa0d81dfb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496378"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="f31fb-102">Metodo ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="f31fb-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="f31fb-103">Ottiene un valore che indica se il debugger è collegato al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f31fb-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f31fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f31fb-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f31fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f31fb-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="f31fb-106">[out] `true` se il debugger è collegato al dominio dell'applicazione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f31fb-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f31fb-107">Note</span><span class="sxs-lookup"><span data-stu-id="f31fb-107">Remarks</span></span>  
 <span data-ttu-id="f31fb-108">Impossibile utilizzare i metodi dell'interfaccia ICorDebugController fino a quando il debugger viene connesso al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f31fb-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f31fb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f31fb-109">Requirements</span></span>  
 <span data-ttu-id="f31fb-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f31fb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f31fb-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f31fb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f31fb-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f31fb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f31fb-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f31fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
