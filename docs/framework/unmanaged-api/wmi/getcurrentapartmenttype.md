---
title: Funzione GetCurrentApartmentType (riferimenti alle API non gestite)
description: La funzione GetCurrentApartmentType Recupera il tipo di Apartment in cui è in esecuzione il chiamante.
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
ms.openlocfilehash: ff64be47802a46979818ab54cc3efb4112dd05e0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798623"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="8e874-103">GetCurrentApartmentType (funzione)</span><span class="sxs-lookup"><span data-stu-id="8e874-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="8e874-104">Recupera il tipo di apartment in cui il chiamante è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8e874-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8e874-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e874-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="8e874-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e874-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8e874-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="8e874-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8e874-108">in Puntatore a un'istanza di [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) .</span><span class="sxs-lookup"><span data-stu-id="8e874-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="8e874-109">out Puntatore a un valore di enumerazione [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) che indica l'Apartment del chiamante.</span><span class="sxs-lookup"><span data-stu-id="8e874-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="8e874-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8e874-110">Return value</span></span>

|<span data-ttu-id="8e874-111">Costante</span><span class="sxs-lookup"><span data-stu-id="8e874-111">Constant</span></span>  |<span data-ttu-id="8e874-112">Value</span><span class="sxs-lookup"><span data-stu-id="8e874-112">Value</span></span>  |<span data-ttu-id="8e874-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e874-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="8e874-114">0</span><span class="sxs-lookup"><span data-stu-id="8e874-114">0</span></span> | <span data-ttu-id="8e874-115">La funzione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8e874-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="8e874-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="8e874-116">0x80000008</span></span> | <span data-ttu-id="8e874-117">Il chiamante non è in esecuzione in un Apartment.</span><span class="sxs-lookup"><span data-stu-id="8e874-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="8e874-118">Note</span><span class="sxs-lookup"><span data-stu-id="8e874-118">Remarks</span></span>

<span data-ttu-id="8e874-119">Questa funzione esegue il wrapping di una chiamata al metodo [IComThreadingInfo:: GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="8e874-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e874-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e874-120">Requirements</span></span>  
 <span data-ttu-id="8e874-121">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e874-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e874-122">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="8e874-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8e874-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8e874-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e874-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e874-124">See also</span></span>

- [<span data-ttu-id="8e874-125">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="8e874-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
