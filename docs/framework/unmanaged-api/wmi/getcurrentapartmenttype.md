---
title: GetCurrentApartmentType function (Unmanaged API Reference)
description: La funzione GetCurrentApartmentType recupera il tipo di apartment in cui è in esecuzione il chiamante.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176825"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="90b18-103">Funzione GetCurrentApartmentType</span><span class="sxs-lookup"><span data-stu-id="90b18-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="90b18-104">Recupera il tipo di apartment in cui il chiamante è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="90b18-104">Retrieves the type of apartment in which the caller is executing.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="90b18-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90b18-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc,
   [in] IComThreadingInfo*    ptr,
   [out] APTTYPE*             aptType
);
```  

## <a name="parameters"></a><span data-ttu-id="90b18-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="90b18-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="90b18-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="90b18-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="90b18-108">[in] Puntatore a [un'istanza di IComThreadingInfo.](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)</span><span class="sxs-lookup"><span data-stu-id="90b18-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="90b18-109">[fuori] Puntatore a un valore di enumerazione [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) che indica l'apartment del chiamante.</span><span class="sxs-lookup"><span data-stu-id="90b18-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="90b18-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="90b18-110">Return value</span></span>

|<span data-ttu-id="90b18-111">Costante</span><span class="sxs-lookup"><span data-stu-id="90b18-111">Constant</span></span>  |<span data-ttu-id="90b18-112">valore</span><span class="sxs-lookup"><span data-stu-id="90b18-112">Value</span></span>  |<span data-ttu-id="90b18-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90b18-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="90b18-114">0</span><span class="sxs-lookup"><span data-stu-id="90b18-114">0</span></span> | <span data-ttu-id="90b18-115">La funzione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="90b18-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="90b18-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="90b18-116">0x80000008</span></span> | <span data-ttu-id="90b18-117">Il chiamante non è in esecuzione in un appartamento.</span><span class="sxs-lookup"><span data-stu-id="90b18-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="90b18-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="90b18-118">Remarks</span></span>

<span data-ttu-id="90b18-119">Questa funzione esegue il wrapping di una chiamata al [metodo IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="90b18-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="90b18-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90b18-120">Requirements</span></span>  
 <span data-ttu-id="90b18-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90b18-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90b18-122">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="90b18-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="90b18-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="90b18-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b18-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90b18-124">See also</span></span>

- [<span data-ttu-id="90b18-125">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="90b18-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
