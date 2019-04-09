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
ms.openlocfilehash: 9ead1c1a91b910e7cfbb09f17ba823fc7a77ce0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181441"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="51059-103">GetCurrentApartmentType (funzione)</span><span class="sxs-lookup"><span data-stu-id="51059-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="51059-104">Recupera il tipo di apartment in cui il chiamante è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="51059-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="51059-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51059-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="51059-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="51059-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="51059-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="51059-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="51059-108">[in] Un puntatore a un [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) istanza.</span><span class="sxs-lookup"><span data-stu-id="51059-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="51059-109">[out] Un puntatore a un [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) valore di enumerazione che indica l'apartment del chiamante.</span><span class="sxs-lookup"><span data-stu-id="51059-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="51059-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="51059-110">Return value</span></span>

|<span data-ttu-id="51059-111">Costante</span><span class="sxs-lookup"><span data-stu-id="51059-111">Constant</span></span>  |<span data-ttu-id="51059-112">Value</span><span class="sxs-lookup"><span data-stu-id="51059-112">Value</span></span>  |<span data-ttu-id="51059-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51059-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="51059-114">0</span><span class="sxs-lookup"><span data-stu-id="51059-114">0</span></span> | <span data-ttu-id="51059-115">La funzione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="51059-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="51059-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="51059-116">0x80000008</span></span> | <span data-ttu-id="51059-117">Il chiamante non è in esecuzione in un apartment.</span><span class="sxs-lookup"><span data-stu-id="51059-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="51059-118">Note</span><span class="sxs-lookup"><span data-stu-id="51059-118">Remarks</span></span>

<span data-ttu-id="51059-119">Questa funzione esegue il wrapping di una chiamata per il [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) (metodo).</span><span class="sxs-lookup"><span data-stu-id="51059-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="51059-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51059-120">Requirements</span></span>  
 <span data-ttu-id="51059-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51059-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51059-122">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="51059-122">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="51059-123">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="51059-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51059-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51059-124">See also</span></span>

- [<span data-ttu-id="51059-125">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="51059-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
