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
ms.openlocfilehash: f0412089fee27e556c2f9230e9b34de3391b9bd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402561"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="a09ac-102">Metodo ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="a09ac-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="a09ac-103">Ottiene un valore che indica se il debugger è collegato al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a09ac-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a09ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a09ac-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a09ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a09ac-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="a09ac-106">[out] `true` se il debugger è collegato al dominio di applicazione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a09ac-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a09ac-107">Note</span><span class="sxs-lookup"><span data-stu-id="a09ac-107">Remarks</span></span>  
 <span data-ttu-id="a09ac-108">Impossibile utilizzare i metodi dell'interfaccia ICorDebugController fino a quando il debugger viene connesso al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a09ac-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a09ac-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a09ac-109">Requirements</span></span>  
 <span data-ttu-id="a09ac-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a09ac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a09ac-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a09ac-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a09ac-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a09ac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a09ac-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a09ac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
