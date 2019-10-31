---
title: Funzione ResetSecurity (riferimenti alle API non gestite)
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
ms.openlocfilehash: 95d91eac21e82e55af2f5e9ab181b770832f5ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120202"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="00c97-103">ResetSecurity (funzione)</span><span class="sxs-lookup"><span data-stu-id="00c97-103">ResetSecurity function</span></span>
<span data-ttu-id="00c97-104">Assegna il token di rappresentazione fornito al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="00c97-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="00c97-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00c97-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="00c97-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="00c97-106">Parameters</span></span>

`token`  
<span data-ttu-id="00c97-107">in Token di rappresentazione da associare al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="00c97-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="00c97-108">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="00c97-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="00c97-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="00c97-109">Return value</span></span>

<span data-ttu-id="00c97-110">Se la funzione ha esito positivo, il valore restituito è `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="00c97-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="00c97-111">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="00c97-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="00c97-112">Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="00c97-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="00c97-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00c97-113">Requirements</span></span>  
 <span data-ttu-id="00c97-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00c97-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00c97-115">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="00c97-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="00c97-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="00c97-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c97-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00c97-117">See also</span></span>

- [<span data-ttu-id="00c97-118">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="00c97-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
