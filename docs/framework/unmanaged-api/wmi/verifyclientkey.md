---
title: Funzione VerifyClientKey (riferimenti alle API non gestite)
description: La funzione VerifyClientKey garantisce che la chiave client disponga della sicurezza corretta.
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
ms.openlocfilehash: b674e959ab93cf76b84e2af41e875a50b7d115f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798195"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="10c56-103">VerifyClientKey (funzione)</span><span class="sxs-lookup"><span data-stu-id="10c56-103">VerifyClientKey function</span></span>
<span data-ttu-id="10c56-104">Verifica che la chiave client includa la sicurezza corretta.</span><span class="sxs-lookup"><span data-stu-id="10c56-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="10c56-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10c56-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="10c56-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="10c56-106">Return value</span></span>

<span data-ttu-id="10c56-107">Se la funzione ha esito positivo, il valore `ERROR_SUCCESS` restituito è (0).</span><span class="sxs-lookup"><span data-stu-id="10c56-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="10c56-108">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito in *Winerror. h*.</span><span class="sxs-lookup"><span data-stu-id="10c56-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="10c56-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10c56-109">Requirements</span></span>  
 <span data-ttu-id="10c56-110">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10c56-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10c56-111">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="10c56-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="10c56-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="10c56-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c56-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10c56-113">See also</span></span>

- [<span data-ttu-id="10c56-114">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="10c56-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
