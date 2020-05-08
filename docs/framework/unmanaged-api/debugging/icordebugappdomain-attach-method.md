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
ms.openlocfilehash: 92cc6c3ce15d8391a43ff130a82476a4363ff5bd
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895304"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="95118-102">Metodo ICorDebugAppDomain::Attach</span><span class="sxs-lookup"><span data-stu-id="95118-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="95118-103">Connette il debugger al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="95118-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95118-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95118-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="95118-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="95118-105">Remarks</span></span>  
 <span data-ttu-id="95118-106">Il debugger deve essere collegato al dominio applicazione per ricevere eventi e per abilitare il debug del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="95118-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95118-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95118-107">Requirements</span></span>  
 <span data-ttu-id="95118-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95118-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95118-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95118-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95118-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95118-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95118-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95118-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
