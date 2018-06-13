---
title: Metodo ICorDebugProcess2::GetVersion
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 nterface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1e1f850e85099a466c497a8fcc822bce9510f69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416380"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="d0192-102">Metodo ICorDebugProcess2::GetVersion</span><span class="sxs-lookup"><span data-stu-id="d0192-102">ICorDebugProcess2::GetVersion Method</span></span>
<span data-ttu-id="d0192-103">Ottiene il numero di versione di common language runtime (CLR) che è in esecuzione in questo processo.</span><span class="sxs-lookup"><span data-stu-id="d0192-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0192-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0192-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] COR_VERSION     *version  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0192-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0192-105">Parameters</span></span>  
 `version`  
 <span data-ttu-id="d0192-106">[out] Un puntatore a una struttura COR_VERSION che archivia il numero di versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="d0192-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0192-107">Note</span><span class="sxs-lookup"><span data-stu-id="d0192-107">Remarks</span></span>  
 <span data-ttu-id="d0192-108">Il `GetVersion` metodo restituisce un codice di errore se è stato caricato alcun runtime nel processo.</span><span class="sxs-lookup"><span data-stu-id="d0192-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0192-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0192-109">Requirements</span></span>  
 <span data-ttu-id="d0192-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0192-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0192-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d0192-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0192-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d0192-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0192-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0192-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
