---
title: Metodo ICorDebugProcess::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: ed7110cb2e2b7a91ed81d2d81c2989d1733c1ee6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207318"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="792e9-102">Metodo ICorDebugProcess::GetHandle</span><span class="sxs-lookup"><span data-stu-id="792e9-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="792e9-103">Ottiene un handle per il processo.</span><span class="sxs-lookup"><span data-stu-id="792e9-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="792e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="792e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="792e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="792e9-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="792e9-106">out Puntatore a un oggetto `HPROCESS` che rappresenta l'handle del processo.</span><span class="sxs-lookup"><span data-stu-id="792e9-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="792e9-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="792e9-107">Remarks</span></span>  
 <span data-ttu-id="792e9-108">L'handle recuperato è di proprietà dell'interfaccia di debug.</span><span class="sxs-lookup"><span data-stu-id="792e9-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="792e9-109">Il debugger deve duplicare l'handle prima di usarlo.</span><span class="sxs-lookup"><span data-stu-id="792e9-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="792e9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="792e9-110">Requirements</span></span>  
 <span data-ttu-id="792e9-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="792e9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="792e9-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="792e9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="792e9-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="792e9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="792e9-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="792e9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
