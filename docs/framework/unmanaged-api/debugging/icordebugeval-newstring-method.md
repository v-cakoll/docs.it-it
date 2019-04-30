---
title: Metodo ICorDebugEval::NewString
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db609bdee7975b6c067271f99529e2cf2240f720
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989027"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="e07c0-102">Metodo ICorDebugEval::NewString</span><span class="sxs-lookup"><span data-stu-id="e07c0-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="e07c0-103">Consente di allocare una nuova istanza di stringa con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="e07c0-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e07c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e07c0-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e07c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e07c0-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="e07c0-106">[in] Puntatore al contenuto della stringa.</span><span class="sxs-lookup"><span data-stu-id="e07c0-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e07c0-107">Note</span><span class="sxs-lookup"><span data-stu-id="e07c0-107">Remarks</span></span>  
 <span data-ttu-id="e07c0-108">La stringa viene sempre creata nel dominio dell'applicazione in cui il thread è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e07c0-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e07c0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e07c0-109">Requirements</span></span>  
 <span data-ttu-id="e07c0-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e07c0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e07c0-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e07c0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e07c0-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e07c0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e07c0-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e07c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
