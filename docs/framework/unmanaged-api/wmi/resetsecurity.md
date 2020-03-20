---
title: ResetSecurity function (Unmanaged API Reference)
description: La funzione ResetSecurity assegna un token di rappresentazione al thread corrente.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: ce74494455c6cc7fe382a4ea4ef2ff0c4e98c61b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174862"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="530a7-103">Funzione ResetSecurity</span><span class="sxs-lookup"><span data-stu-id="530a7-103">ResetSecurity function</span></span>
<span data-ttu-id="530a7-104">Assegna il token di rappresentazione fornito al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="530a7-104">Assigns the supplied impersonation token to the current thread.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="530a7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="530a7-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a><span data-ttu-id="530a7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="530a7-106">Parameters</span></span>

`token`  
<span data-ttu-id="530a7-107">[in] Token di rappresentazione da associare al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="530a7-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="530a7-108">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="530a7-108">Its value can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="530a7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="530a7-109">Return value</span></span>

<span data-ttu-id="530a7-110">Se la funzione ha esito `S_OK` positivo, il valore restituito è (0).</span><span class="sxs-lookup"><span data-stu-id="530a7-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="530a7-111">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="530a7-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="530a7-112">Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo.To](geterrorinfo.md) get extended error information, call the GetErrorInfo function.</span><span class="sxs-lookup"><span data-stu-id="530a7-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="530a7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="530a7-113">Requirements</span></span>  
 <span data-ttu-id="530a7-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="530a7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="530a7-115">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="530a7-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="530a7-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="530a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="530a7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="530a7-117">See also</span></span>

- [<span data-ttu-id="530a7-118">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="530a7-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
