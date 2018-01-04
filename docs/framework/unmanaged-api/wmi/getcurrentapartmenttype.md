---
title: Funzione GetCurrentApartmentType (riferimenti alle API non gestite)
description: "La funzione GetCurrentApartmentType recupera il tipo di apartment, in cui il chiamante è in esecuzione."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetCurrentApartmentType
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetCurrentApartmentType
helpviewer_keywords: GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a42c6c3c778dbdefd4b83621e65b81741b940ebe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="ba607-103">GetCurrentApartmentType (funzione)</span><span class="sxs-lookup"><span data-stu-id="ba607-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="ba607-104">Recupera il tipo di apartment, in cui il chiamante è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ba607-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ba607-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba607-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="ba607-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba607-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ba607-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ba607-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ba607-108">[in] Un puntatore a un [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="ba607-108">[in] A pointer to an [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) instance.</span></span>

`aptType`  
<span data-ttu-id="ba607-109">[out] Un puntatore a un [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) valore di enumerazione che indica l'apartment del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ba607-109">[out] A pointer to an [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="ba607-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba607-110">Return value</span></span>


|<span data-ttu-id="ba607-111">Costante</span><span class="sxs-lookup"><span data-stu-id="ba607-111">Constant</span></span>  |<span data-ttu-id="ba607-112">Valore</span><span class="sxs-lookup"><span data-stu-id="ba607-112">Value</span></span>  |<span data-ttu-id="ba607-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba607-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="ba607-114">0</span><span class="sxs-lookup"><span data-stu-id="ba607-114">0</span></span> | <span data-ttu-id="ba607-115">La funzione completata.</span><span class="sxs-lookup"><span data-stu-id="ba607-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="ba607-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="ba607-116">0x80000008</span></span> | <span data-ttu-id="ba607-117">Il chiamante non è in esecuzione in un apartment.</span><span class="sxs-lookup"><span data-stu-id="ba607-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="ba607-118">Note</span><span class="sxs-lookup"><span data-stu-id="ba607-118">Remarks</span></span>

<span data-ttu-id="ba607-119">Questa funzione esegue il wrapping di una chiamata al [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="ba607-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba607-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba607-120">Requirements</span></span>  
 <span data-ttu-id="ba607-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba607-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba607-122">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ba607-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ba607-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ba607-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba607-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba607-124">See also</span></span>  
[<span data-ttu-id="ba607-125">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ba607-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
