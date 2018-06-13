---
title: Funzione GetErrorInfo (riferimenti alle API non gestite)
description: La funzione GetErrorInfo recupera informazioni sull'errore nella chiamata alla funzione precedente.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef52a4e503597e08eae407571f02bf63adafc4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455957"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="a0320-103">GetErrorInfo (funzione)</span><span class="sxs-lookup"><span data-stu-id="a0320-103">GetErrorInfo function</span></span>
<span data-ttu-id="a0320-104">Recupera informazioni sull'errore nella chiamata alla funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="a0320-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a0320-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0320-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="a0320-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a0320-106">Return value</span></span>

<span data-ttu-id="a0320-107">Un puntatore a un [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) oggetto se la chiamata di funzione ha esito positivo, o `null` in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="a0320-107">An pointer to an [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a0320-108">Note</span><span class="sxs-lookup"><span data-stu-id="a0320-108">Remarks</span></span>

<span data-ttu-id="a0320-109">Questa funzione esegue il wrapping di una chiamata al [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="a0320-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0320-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0320-110">Requirements</span></span>  
 <span data-ttu-id="a0320-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0320-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0320-112">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="a0320-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="a0320-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a0320-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0320-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0320-114">See also</span></span>  
[<span data-ttu-id="a0320-115">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="a0320-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
