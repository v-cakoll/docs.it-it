---
title: Funzione SetSecurity (riferimenti alle API non gestite)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7200e3a19fcadabb5e149c38b620b3f60907c392
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377417"
---
# <a name="setsecurity-function"></a><span data-ttu-id="510b2-103">SetSecurity (funzione)</span><span class="sxs-lookup"><span data-stu-id="510b2-103">SetSecurity function</span></span>

<span data-ttu-id="510b2-104">Recupera il token di rappresentazione associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="510b2-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="510b2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="510b2-105">Syntax</span></span>

```
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="510b2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="510b2-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="510b2-107">[out] Quando la funzione viene restituito, contiene un puntatore a un `boolean` che indica se il token deve essere reimpostato tramite una chiamata di [ResetSecurity](resetsecurity.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="510b2-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="510b2-108">[out] Quando la funzione viene restituito, contiene un puntatore all'handle del token di rappresentazione associate al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="510b2-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="510b2-109">Il valore può essere `null` se non vi è alcun token associato al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="510b2-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="510b2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="510b2-110">Return value</span></span>

<span data-ttu-id="510b2-111">Se la funzione ha esito positivo, il valore restituito è `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="510b2-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="510b2-112">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="510b2-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="510b2-113">Per ottenere informazioni sull'errore, chiamare il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="510b2-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="510b2-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="510b2-114">Requirements</span></span>

 <span data-ttu-id="510b2-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="510b2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="510b2-116">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="510b2-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="510b2-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="510b2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="510b2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="510b2-118">See also</span></span>

- [<span data-ttu-id="510b2-119">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="510b2-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)