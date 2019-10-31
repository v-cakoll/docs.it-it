---
title: Funzione di sicurezza (riferimenti alle API non gestite)
description: La funzione di sicurezza recupera il token di rappresentazione del thread corrente.
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
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120221"
---
# <a name="setsecurity-function"></a><span data-ttu-id="3bdc5-103">Funzione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3bdc5-103">SetSecurity function</span></span>

<span data-ttu-id="3bdc5-104">Recupera il token di rappresentazione associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3bdc5-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3bdc5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3bdc5-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="3bdc5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3bdc5-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="3bdc5-107">out Quando la funzione restituisce un valore, contiene un puntatore a un `boolean` che indica se il token deve essere reimpostato chiamando la funzione [ResetSecurity](resetsecurity.md) .</span><span class="sxs-lookup"><span data-stu-id="3bdc5-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="3bdc5-108">out Quando la funzione restituisce un valore, contiene un puntatore all'handle del token di rappresentazione associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="3bdc5-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="3bdc5-109">Il valore può essere `null` se al thread corrente non è associato alcun token.</span><span class="sxs-lookup"><span data-stu-id="3bdc5-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="3bdc5-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3bdc5-110">Return value</span></span>

<span data-ttu-id="3bdc5-111">Se la funzione ha esito positivo, il valore restituito è `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="3bdc5-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="3bdc5-112">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="3bdc5-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="3bdc5-113">Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="3bdc5-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="3bdc5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3bdc5-114">Requirements</span></span>

 <span data-ttu-id="3bdc5-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bdc5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="3bdc5-116">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="3bdc5-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="3bdc5-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3bdc5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3bdc5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bdc5-118">See also</span></span>

- [<span data-ttu-id="3bdc5-119">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="3bdc5-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
