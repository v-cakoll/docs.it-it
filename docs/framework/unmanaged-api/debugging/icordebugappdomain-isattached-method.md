---
title: Metodo ICorDebugAppDomain::IsAttached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.IsAttached
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a85b674ad705f77e00cf2a8a5286d6a74f7a646
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="0584e-102">Metodo ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="0584e-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="0584e-103">Ottiene un valore che indica se il debugger è collegato al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="0584e-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0584e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0584e-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0584e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0584e-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="0584e-106">[out] `true` se il debugger è collegato al dominio di applicazione; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0584e-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0584e-107">Note</span><span class="sxs-lookup"><span data-stu-id="0584e-107">Remarks</span></span>  
 <span data-ttu-id="0584e-108">Impossibile utilizzare i metodi dell'interfaccia ICorDebugController fino a quando il debugger viene connesso al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="0584e-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0584e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0584e-109">Requirements</span></span>  
 <span data-ttu-id="0584e-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0584e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0584e-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0584e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0584e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0584e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0584e-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0584e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
