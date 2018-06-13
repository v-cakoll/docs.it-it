---
title: Metodo ICorDebugAssembly::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1c3bcc0ed22fa970d92e2384277d0786016db19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402109"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="1f32a-102">Metodo ICorDebugAssembly::GetProcess</span><span class="sxs-lookup"><span data-stu-id="1f32a-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="1f32a-103">Ottiene un puntatore a interfaccia per il processo in cui è in esecuzione questa istanza di ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="1f32a-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f32a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f32a-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f32a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1f32a-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="1f32a-106">[out] Puntatore a interfaccia ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="1f32a-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f32a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f32a-107">Requirements</span></span>  
 <span data-ttu-id="1f32a-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f32a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f32a-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1f32a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f32a-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1f32a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f32a-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f32a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
