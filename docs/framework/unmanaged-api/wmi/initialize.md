---
title: Funzione Initialize (riferimenti alle API non gestite)
description: La funzione Initialize esegue l'inizializzazione WMI.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127386"
---
# <a name="initialize-function"></a><span data-ttu-id="f5e5a-103">Initialize (funzione)</span><span class="sxs-lookup"><span data-stu-id="f5e5a-103">Initialize function</span></span>

<span data-ttu-id="f5e5a-104">Esegue l'inizializzazione di WMI.</span><span class="sxs-lookup"><span data-stu-id="f5e5a-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f5e5a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5e5a-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="f5e5a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5e5a-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="f5e5a-107">[in] `true` per indicare che le chiamate a QueryInterface sugli oggetti WMI sono consentite; in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="f5e5a-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="f5e5a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f5e5a-108">Return value</span></span>

<span data-ttu-id="f5e5a-109">La funzione restituisce sempre `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="f5e5a-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="f5e5a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5e5a-110">Requirements</span></span>

<span data-ttu-id="f5e5a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e5a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f5e5a-112">**Intestazione:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="f5e5a-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="f5e5a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f5e5a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f5e5a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5e5a-114">See also</span></span>

- [<span data-ttu-id="f5e5a-115">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="f5e5a-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
