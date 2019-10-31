---
title: Metodo ICorDebugAppDomain::Attach
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: 66ec64b1a855a3d31f14f3ef29dde0b82361f5d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133975"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="1f260-102">Metodo ICorDebugAppDomain::Attach</span><span class="sxs-lookup"><span data-stu-id="1f260-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="1f260-103">Connette il debugger al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f260-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f260-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f260-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1f260-105">Note</span><span class="sxs-lookup"><span data-stu-id="1f260-105">Remarks</span></span>  
 <span data-ttu-id="1f260-106">Il debugger deve essere collegato al dominio applicazione per ricevere eventi e per abilitare il debug del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f260-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f260-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f260-107">Requirements</span></span>  
 <span data-ttu-id="1f260-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f260-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f260-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f260-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f260-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f260-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f260-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f260-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
