---
title: Metodo ICorDebugReferenceValue::Dereference
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.Dereference
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4eb3287612a8301d551a1443d803e60e4d03f7db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="def26-102">Metodo ICorDebugReferenceValue::Dereference</span><span class="sxs-lookup"><span data-stu-id="def26-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="def26-103">Ottiene l'oggetto a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="def26-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="def26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="def26-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="def26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="def26-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="def26-106">[out] Un puntatore all'indirizzo di un'interfaccia ICorDebugValue che rappresenta l'oggetto a cui fa riferimento questo oggetto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="def26-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="def26-107">Note</span><span class="sxs-lookup"><span data-stu-id="def26-107">Remarks</span></span>  
 <span data-ttu-id="def26-108">Il `ICorDebugValue` oggetto è valido solo mentre il relativo riferimento non è ancora stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="def26-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="def26-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="def26-109">Requirements</span></span>  
 <span data-ttu-id="def26-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="def26-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="def26-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="def26-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="def26-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="def26-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="def26-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="def26-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
