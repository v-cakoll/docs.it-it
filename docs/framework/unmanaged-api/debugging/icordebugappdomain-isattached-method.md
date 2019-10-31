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
ms.openlocfilehash: 30e0b0c4ed9bac4abd1dc185031e41c1e3ed014a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134665"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="79c8a-102">Metodo ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="79c8a-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="79c8a-103">Ottiene un valore che indica se il debugger è collegato al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="79c8a-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79c8a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79c8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79c8a-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="79c8a-106">[out] `true` se il debugger è collegato al dominio applicazione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="79c8a-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79c8a-107">Note</span><span class="sxs-lookup"><span data-stu-id="79c8a-107">Remarks</span></span>  
 <span data-ttu-id="79c8a-108">I metodi ICorDebugController non possono essere usati finché il debugger non si connette al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="79c8a-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79c8a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79c8a-109">Requirements</span></span>  
 <span data-ttu-id="79c8a-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79c8a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79c8a-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79c8a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79c8a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79c8a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79c8a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79c8a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
