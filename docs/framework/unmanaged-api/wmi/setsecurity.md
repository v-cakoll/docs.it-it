---
title: SetSecurity function (Unmanaged API Reference)
description: La funzione SetSecurity recupera il token di rappresentazione del thread corrente.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176734"
---
# <a name="setsecurity-function"></a><span data-ttu-id="170c7-103">Funzione SetSecurity</span><span class="sxs-lookup"><span data-stu-id="170c7-103">SetSecurity function</span></span>

<span data-ttu-id="170c7-104">Recupera il token di rappresentazione associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="170c7-104">Retrieves the impersonation token associated with the current thread.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="170c7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="170c7-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a><span data-ttu-id="170c7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="170c7-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="170c7-107">[fuori] Quando la funzione restituisce, `boolean` contiene un puntatore a un che indica se il token deve essere reimpostato chiamando il [ResetSecurity](resetsecurity.md) funzione.</span><span class="sxs-lookup"><span data-stu-id="170c7-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="170c7-108">[fuori] Quando la funzione restituisce, contiene un puntatore all'handle del token di rappresentazione associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="170c7-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="170c7-109">Il valore `null` può essere se non è presente alcun token associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="170c7-109">Its value can be `null` if there is no token associated with the current thread.</span></span>

## <a name="return-value"></a><span data-ttu-id="170c7-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="170c7-110">Return value</span></span>

<span data-ttu-id="170c7-111">Se la funzione ha esito `S_OK` positivo, il valore restituito è (0).</span><span class="sxs-lookup"><span data-stu-id="170c7-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="170c7-112">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="170c7-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="170c7-113">Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo.To](geterrorinfo.md) get extended error information, call the GetErrorInfo function.</span><span class="sxs-lookup"><span data-stu-id="170c7-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="170c7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="170c7-114">Requirements</span></span>

 <span data-ttu-id="170c7-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="170c7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="170c7-116">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="170c7-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="170c7-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="170c7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="170c7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="170c7-118">See also</span></span>

- [<span data-ttu-id="170c7-119">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="170c7-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
