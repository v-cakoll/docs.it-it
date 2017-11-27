---
title: Funzione VerifyClientKey (riferimenti alle API non gestite)
description: La funzione di VerifyClientKey garantisce che la chiave di client ha la sicurezza corretta.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: VerifyClientKey
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: VerifyClientKey
helpviewer_keywords: VerifyClientKey function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cce10e3dd5536a85b4dee62cc7f6e9e8e73929cb
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="685aa-103">VerifyClientKey (funzione)</span><span class="sxs-lookup"><span data-stu-id="685aa-103">VerifyClientKey function</span></span>
<span data-ttu-id="685aa-104">Assicura che la chiave client disponga di sicurezza corrette.</span><span class="sxs-lookup"><span data-stu-id="685aa-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="685aa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="685aa-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="685aa-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="685aa-106">Return value</span></span>

<span data-ttu-id="685aa-107">Se la funzione ha esito positivo, il valore restituito è `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="685aa-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="685aa-108">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito in *Winerror*.</span><span class="sxs-lookup"><span data-stu-id="685aa-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="685aa-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="685aa-109">Requirements</span></span>  
 <span data-ttu-id="685aa-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="685aa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="685aa-111">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="685aa-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="685aa-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="685aa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685aa-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="685aa-113">See also</span></span>  
[<span data-ttu-id="685aa-114">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="685aa-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
