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
ms.openlocfilehash: 50a18f435063b74b837dbfe9e4f1d986bb735039
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753349"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="6a412-102">Metodo ICorDebugEval::NewString</span><span class="sxs-lookup"><span data-stu-id="6a412-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="6a412-103">Consente di allocare una nuova istanza di stringa con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="6a412-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a412-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a412-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a412-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6a412-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="6a412-106">[in] Puntatore al contenuto della stringa.</span><span class="sxs-lookup"><span data-stu-id="6a412-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a412-107">Note</span><span class="sxs-lookup"><span data-stu-id="6a412-107">Remarks</span></span>  
 <span data-ttu-id="6a412-108">La stringa viene sempre creata nel dominio dell'applicazione in cui il thread è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6a412-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a412-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a412-109">Requirements</span></span>  
 <span data-ttu-id="6a412-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a412-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a412-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a412-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a412-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a412-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a412-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a412-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
