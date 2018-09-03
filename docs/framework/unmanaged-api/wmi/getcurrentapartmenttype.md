---
title: Funzione GetCurrentApartmentType (riferimenti alle API non gestite)
description: La funzione GetCurrentApartmentType recupera il tipo di apartment in cui è in esecuzione al chiamante.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4de85eb310de70dc8fd61f7c06abca95ec267f87
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463091"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="ed0ae-103">GetCurrentApartmentType (funzione)</span><span class="sxs-lookup"><span data-stu-id="ed0ae-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="ed0ae-104">Recupera il tipo di apartment in cui è in esecuzione al chiamante.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ed0ae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed0ae-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="ed0ae-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed0ae-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ed0ae-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ed0ae-108">[in] Un puntatore a un [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) istanza.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="ed0ae-109">[out] Un puntatore a un [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) valore di enumerazione che indica l'apartment del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="ed0ae-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ed0ae-110">Return value</span></span>


|<span data-ttu-id="ed0ae-111">Costante</span><span class="sxs-lookup"><span data-stu-id="ed0ae-111">Constant</span></span>  |<span data-ttu-id="ed0ae-112">Valore</span><span class="sxs-lookup"><span data-stu-id="ed0ae-112">Value</span></span>  |<span data-ttu-id="ed0ae-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed0ae-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="ed0ae-114">0</span><span class="sxs-lookup"><span data-stu-id="ed0ae-114">0</span></span> | <span data-ttu-id="ed0ae-115">La funzione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="ed0ae-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="ed0ae-116">0x80000008</span></span> | <span data-ttu-id="ed0ae-117">Il chiamante non è in esecuzione in un apartment.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="ed0ae-118">Note</span><span class="sxs-lookup"><span data-stu-id="ed0ae-118">Remarks</span></span>

<span data-ttu-id="ed0ae-119">Questa funzione esegue il wrapping di una chiamata per il [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ed0ae-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed0ae-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed0ae-120">Requirements</span></span>  
 <span data-ttu-id="ed0ae-121">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed0ae-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed0ae-122">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ed0ae-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ed0ae-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ed0ae-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0ae-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed0ae-124">See also</span></span>  
[<span data-ttu-id="ed0ae-125">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ed0ae-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
