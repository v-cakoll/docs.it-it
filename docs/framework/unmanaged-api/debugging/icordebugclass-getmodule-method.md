---
title: Metodo ICorDebugClass::GetModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8021eb63b33f653e5b8c8a16d2e181223d5ee2b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="8e783-102">Metodo ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="8e783-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="8e783-103">Ottiene il modulo che definisce questa classe.</span><span class="sxs-lookup"><span data-stu-id="8e783-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e783-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e783-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e783-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e783-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="8e783-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo in cui questa classe è definita.</span><span class="sxs-lookup"><span data-stu-id="8e783-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e783-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e783-107">Requirements</span></span>  
 <span data-ttu-id="8e783-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e783-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e783-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8e783-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e783-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e783-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e783-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e783-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
