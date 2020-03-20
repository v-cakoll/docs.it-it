---
title: GetErrorInfo (riferimento all'API non gestita)
description: La funzione GetErrorInfo recupera le informazioni sull'errore dalla chiamata di funzione precedente.
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
ms.openlocfilehash: 802ee66a5be213ac7a599b193ec6de589773ea17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176812"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="af36a-103">Funzione GetErrorInfo</span><span class="sxs-lookup"><span data-stu-id="af36a-103">GetErrorInfo function</span></span>
<span data-ttu-id="af36a-104">Recupera le informazioni di errore dalla chiamata di funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="af36a-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="af36a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af36a-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="af36a-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="af36a-106">Return value</span></span>

<span data-ttu-id="af36a-107">Puntatore a un [oggetto IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) se la `null` chiamata di funzione ha esito positivo o se ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="af36a-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="af36a-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="af36a-108">Remarks</span></span>

<span data-ttu-id="af36a-109">Questa funzione esegue il wrapping di una chiamata al [metodo IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="af36a-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="af36a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af36a-110">Requirements</span></span>  
 <span data-ttu-id="af36a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af36a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af36a-112">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="af36a-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="af36a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="af36a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af36a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af36a-114">See also</span></span>

- [<span data-ttu-id="af36a-115">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="af36a-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
