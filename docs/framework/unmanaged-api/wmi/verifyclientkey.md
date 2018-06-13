---
title: Funzione VerifyClientKey (riferimenti alle API non gestite)
description: La funzione di VerifyClientKey garantisce che la chiave di client ha la sicurezza corretta.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea8a74633d3e950f6cf7ba87c00a9efa45206545
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459564"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="10240-103">VerifyClientKey (funzione)</span><span class="sxs-lookup"><span data-stu-id="10240-103">VerifyClientKey function</span></span>
<span data-ttu-id="10240-104">Assicura che la chiave client disponga di sicurezza corrette.</span><span class="sxs-lookup"><span data-stu-id="10240-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="10240-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10240-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="10240-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="10240-106">Return value</span></span>

<span data-ttu-id="10240-107">Se la funzione ha esito positivo, il valore restituito è `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="10240-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="10240-108">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito in *Winerror*.</span><span class="sxs-lookup"><span data-stu-id="10240-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="10240-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10240-109">Requirements</span></span>  
 <span data-ttu-id="10240-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10240-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10240-111">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="10240-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="10240-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="10240-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10240-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10240-113">See also</span></span>  
[<span data-ttu-id="10240-114">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="10240-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
