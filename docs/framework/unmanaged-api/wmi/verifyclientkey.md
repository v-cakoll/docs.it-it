---
title: Funzione VerifyClientKey (riferimenti alle API non gestite)
description: La funzione VerifyClientKey garantisce che la chiave client ha la sicurezza corretta.
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
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214715"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="dc607-103">VerifyClientKey (funzione)</span><span class="sxs-lookup"><span data-stu-id="dc607-103">VerifyClientKey function</span></span>
<span data-ttu-id="dc607-104">Verifica che la chiave client includa la sicurezza corretta.</span><span class="sxs-lookup"><span data-stu-id="dc607-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="dc607-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc607-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="dc607-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dc607-106">Return value</span></span>

<span data-ttu-id="dc607-107">Se la funzione ha esito positivo, il valore restituito è `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="dc607-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="dc607-108">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito nella *Winerror*.</span><span class="sxs-lookup"><span data-stu-id="dc607-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="dc607-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc607-109">Requirements</span></span>  
 <span data-ttu-id="dc607-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc607-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc607-111">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="dc607-111">**Header:** WMINet_Utils.def</span></span>  
  
 **<span data-ttu-id="dc607-112">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dc607-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dc607-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc607-113">See also</span></span>

- [<span data-ttu-id="dc607-114">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="dc607-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
