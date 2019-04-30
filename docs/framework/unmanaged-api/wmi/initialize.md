---
title: Initialize (funzione) (riferimenti alle API non gestite)
description: La funzione di inizializzazione esegue l'inizializzazione di WMI.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c71b2b6d6f102d19d30d480ee9bafcac3c204be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049297"
---
# <a name="initialize-function"></a><span data-ttu-id="cb0ed-103">Initialize (funzione)</span><span class="sxs-lookup"><span data-stu-id="cb0ed-103">Initialize function</span></span>

<span data-ttu-id="cb0ed-104">Esegue l'inizializzazione di WMI.</span><span class="sxs-lookup"><span data-stu-id="cb0ed-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cb0ed-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb0ed-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="cb0ed-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb0ed-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="cb0ed-107">[in] `true` per indicare che sono consentite le chiamate a QueryInterface sugli oggetti WMI. `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="cb0ed-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="cb0ed-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cb0ed-108">Return value</span></span>

<span data-ttu-id="cb0ed-109">La funzione restituisce sempre `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="cb0ed-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="cb0ed-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb0ed-110">Requirements</span></span>

<span data-ttu-id="cb0ed-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb0ed-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="cb0ed-112">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="cb0ed-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="cb0ed-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cb0ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cb0ed-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb0ed-114">See also</span></span>

- [<span data-ttu-id="cb0ed-115">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="cb0ed-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
