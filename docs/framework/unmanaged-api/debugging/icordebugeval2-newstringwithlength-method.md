---
title: Metodo ICorDebugEval2::NewStringWithLength
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewStringWithLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1cd2bc201210bc9af8c13c83553b581c080f658a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="79ca7-102">Metodo ICorDebugEval2::NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="79ca7-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="79ca7-103">Crea una stringa di lunghezza specificata, con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="79ca7-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ca7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79ca7-104">Syntax</span></span>  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79ca7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79ca7-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="79ca7-106">[in] Puntatore al valore stringa.</span><span class="sxs-lookup"><span data-stu-id="79ca7-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="79ca7-107">[in] Lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="79ca7-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79ca7-108">Note</span><span class="sxs-lookup"><span data-stu-id="79ca7-108">Remarks</span></span>  
 <span data-ttu-id="79ca7-109">Se finale della stringa deve essere nella stringa gestita, il chiamante del carattere null di `NewStringWithLength` metodo è necessario assicurarsi che la lunghezza della stringa include il carattere null finale.</span><span class="sxs-lookup"><span data-stu-id="79ca7-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="79ca7-110">La stringa viene sempre creata nel dominio dell'applicazione in cui il thread è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="79ca7-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79ca7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79ca7-111">Requirements</span></span>  
 <span data-ttu-id="79ca7-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79ca7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79ca7-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="79ca7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79ca7-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79ca7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79ca7-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79ca7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
