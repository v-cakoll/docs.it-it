---
title: Funzione ResetSecurity (riferimenti alle API non gestite)
description: La funzione ResetSecurity assegna un token di rappresentazione per il thread corrente.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e937690c184d810549e8ab11ef1fc2273a45c5f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049245"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="f79ae-103">ResetSecurity (funzione)</span><span class="sxs-lookup"><span data-stu-id="f79ae-103">ResetSecurity function</span></span>
<span data-ttu-id="f79ae-104">Assegna il token di rappresentazione fornito al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="f79ae-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f79ae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f79ae-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="f79ae-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f79ae-106">Parameters</span></span>

`token`  
<span data-ttu-id="f79ae-107">[in] Il token di rappresentazione da associare al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="f79ae-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="f79ae-108">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="f79ae-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="f79ae-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f79ae-109">Return value</span></span>

<span data-ttu-id="f79ae-110">Se la funzione ha esito positivo, il valore restituito è `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="f79ae-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="f79ae-111">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="f79ae-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="f79ae-112">Per ottenere informazioni sull'errore, chiamare il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="f79ae-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f79ae-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f79ae-113">Requirements</span></span>  
 <span data-ttu-id="f79ae-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f79ae-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f79ae-115">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f79ae-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f79ae-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f79ae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f79ae-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f79ae-117">See also</span></span>

- [<span data-ttu-id="f79ae-118">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="f79ae-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
