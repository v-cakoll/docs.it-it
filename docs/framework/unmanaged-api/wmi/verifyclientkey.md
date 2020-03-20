---
title: VerifyClientKey (riferimento all'API non gestita)
description: La funzione VerifyClientKey garantisce la sicurezza corretta della chiave client.
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
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176708"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="34584-103">VerifyClientKey (funzione)</span><span class="sxs-lookup"><span data-stu-id="34584-103">VerifyClientKey function</span></span>
<span data-ttu-id="34584-104">Verifica che la chiave client includa la sicurezza corretta.</span><span class="sxs-lookup"><span data-stu-id="34584-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="34584-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34584-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="34584-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="34584-106">Return value</span></span>

<span data-ttu-id="34584-107">Se la funzione ha esito `ERROR_SUCCESS` positivo, il valore restituito è (0).</span><span class="sxs-lookup"><span data-stu-id="34584-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="34584-108">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito in *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="34584-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="34584-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34584-109">Requirements</span></span>  
 <span data-ttu-id="34584-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34584-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34584-111">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="34584-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="34584-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="34584-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34584-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34584-113">See also</span></span>

- [<span data-ttu-id="34584-114">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="34584-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
