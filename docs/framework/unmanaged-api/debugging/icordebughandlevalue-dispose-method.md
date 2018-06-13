---
title: Metodo ICorDebugHandleValue::Dispose
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.Dispose
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::Dispose
helpviewer_keywords:
- ICorDebugHandleValue::Dispose method [.NET Framework debugging]
- Dispose method [.NET Framework debugging]
ms.assetid: c1542811-0a7f-4235-bcfd-b24370d6f24b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9114799b87d39333ff9da66429dc1ea99ec2131c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413430"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="3ad41-102">Metodo ICorDebugHandleValue::Dispose</span><span class="sxs-lookup"><span data-stu-id="3ad41-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="3ad41-103">Rilascia l'handle di cui fa riferimento l'oggetto ICorDebugHandleValue senza rilasciare esplicitamente il puntatore di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3ad41-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ad41-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ad41-104">Syntax</span></span>  
  
```  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="3ad41-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ad41-105">Requirements</span></span>  
 <span data-ttu-id="3ad41-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ad41-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ad41-107">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3ad41-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ad41-108">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3ad41-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ad41-109">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ad41-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
