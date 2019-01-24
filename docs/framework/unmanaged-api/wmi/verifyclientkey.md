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
ms.openlocfilehash: 94d601125049f0c215b3b03bf8b13d2959872c3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711759"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="29b4a-103">VerifyClientKey (funzione)</span><span class="sxs-lookup"><span data-stu-id="29b4a-103">VerifyClientKey function</span></span>
<span data-ttu-id="29b4a-104">Verifica che la chiave client includa la sicurezza corretta.</span><span class="sxs-lookup"><span data-stu-id="29b4a-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="29b4a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29b4a-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="29b4a-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="29b4a-106">Return value</span></span>

<span data-ttu-id="29b4a-107">Se la funzione ha esito positivo, il valore restituito è `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="29b4a-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="29b4a-108">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito nella *Winerror*.</span><span class="sxs-lookup"><span data-stu-id="29b4a-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="29b4a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29b4a-109">Requirements</span></span>  
 <span data-ttu-id="29b4a-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29b4a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29b4a-111">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="29b4a-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="29b4a-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="29b4a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b4a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29b4a-113">See also</span></span>
- [<span data-ttu-id="29b4a-114">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="29b4a-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
