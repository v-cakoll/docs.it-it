---
title: 'IMetaDataImport:: GetErrorInfo (funzione) (riferimenti alle API non gestite)'
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b27dae07697943c696dc3419f2414701feb1220
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577672"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="124a1-103">GetErrorInfo (funzione)</span><span class="sxs-lookup"><span data-stu-id="124a1-103">GetErrorInfo function</span></span>
<span data-ttu-id="124a1-104">Recupera le informazioni di errore dalla chiamata di funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="124a1-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="124a1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="124a1-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="124a1-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="124a1-106">Return value</span></span>

<span data-ttu-id="124a1-107">Un puntatore a un [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) oggetto se la chiamata di funzione ha esito positivo, o `null` se ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="124a1-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="124a1-108">Note</span><span class="sxs-lookup"><span data-stu-id="124a1-108">Remarks</span></span>

<span data-ttu-id="124a1-109">Questa funzione esegue il wrapping di una chiamata per il [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) (metodo).</span><span class="sxs-lookup"><span data-stu-id="124a1-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="124a1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="124a1-110">Requirements</span></span>  
 <span data-ttu-id="124a1-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="124a1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="124a1-112">**Intestazione:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="124a1-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="124a1-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="124a1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="124a1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="124a1-114">See also</span></span>
- [<span data-ttu-id="124a1-115">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="124a1-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
