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
ms.openlocfilehash: 8a5d421bf0eb8ec5a34fe21d6efc79bbe56c294c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137649"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="f7574-102">Metodo ICorDebugEval::NewString</span><span class="sxs-lookup"><span data-stu-id="f7574-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="f7574-103">Alloca una nuova istanza di stringa con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="f7574-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7574-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7574-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7574-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7574-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="f7574-106">in Puntatore al contenuto della stringa.</span><span class="sxs-lookup"><span data-stu-id="f7574-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7574-107">Note</span><span class="sxs-lookup"><span data-stu-id="f7574-107">Remarks</span></span>  
 <span data-ttu-id="f7574-108">La stringa viene sempre creata nel dominio applicazione in cui è attualmente in esecuzione il thread.</span><span class="sxs-lookup"><span data-stu-id="f7574-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7574-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7574-109">Requirements</span></span>  
 <span data-ttu-id="f7574-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7574-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7574-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7574-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7574-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7574-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7574-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7574-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
