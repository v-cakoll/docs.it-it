---
title: Funzione QualifierSet_Get (riferimenti alle API non gestite)
description: La funzione QualifierSet_Get Ottiene un qualificatore denominato.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93ba4e59dda4806931ba085f8c63b63a1d8bd797
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="1c963-103">QualifierSet_Get (funzione)</span><span class="sxs-lookup"><span data-stu-id="1c963-103">QualifierSet_Get function</span></span>
<span data-ttu-id="1c963-104">Ottiene il qualificatore denominato specificato.</span><span class="sxs-lookup"><span data-stu-id="1c963-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1c963-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c963-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="1c963-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c963-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="1c963-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="1c963-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="1c963-108">[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="1c963-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="1c963-109">[in] Il nome del qualificatore il cui valore è richiesto.</span><span class="sxs-lookup"><span data-stu-id="1c963-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="1c963-110">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="1c963-110">[in] Reserved.</span></span> <span data-ttu-id="1c963-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="1c963-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="1c963-112">[out] Al termine, il tipo corretto e il valore per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="1c963-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="1c963-113">Se la funzione ha esito negativo, il `VARIANT` a cui puntava `pVal` non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="1c963-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="1c963-114">Se questo parametro è `null`, il parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="1c963-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="1c963-115">[out] Puntatore a un valore LONG che riceve i bit flavor qualificatore per il qualificatore richiesto.</span><span class="sxs-lookup"><span data-stu-id="1c963-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="1c963-116">Se non si desiderano informazioni di versione, questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="1c963-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="1c963-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1c963-117">Return value</span></span>

<span data-ttu-id="1c963-118">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="1c963-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1c963-119">Costante</span><span class="sxs-lookup"><span data-stu-id="1c963-119">Constant</span></span>  |<span data-ttu-id="1c963-120">Valore</span><span class="sxs-lookup"><span data-stu-id="1c963-120">Value</span></span>  |<span data-ttu-id="1c963-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c963-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1c963-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1c963-122">0x80041008</span></span> | <span data-ttu-id="1c963-123">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="1c963-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="1c963-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1c963-124">0x80041002</span></span> | <span data-ttu-id="1c963-125">Il qualificatore specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="1c963-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1c963-126">0</span><span class="sxs-lookup"><span data-stu-id="1c963-126">0</span></span> | <span data-ttu-id="1c963-127">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1c963-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1c963-128">Note</span><span class="sxs-lookup"><span data-stu-id="1c963-128">Remarks</span></span>

<span data-ttu-id="1c963-129">Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="1c963-129">This function wraps a call to the [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c963-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c963-130">Requirements</span></span>  
 <span data-ttu-id="1c963-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c963-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c963-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1c963-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1c963-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1c963-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c963-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c963-134">See also</span></span>  
[<span data-ttu-id="1c963-135">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1c963-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
