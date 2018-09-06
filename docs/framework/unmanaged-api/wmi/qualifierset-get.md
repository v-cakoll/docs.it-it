---
title: Funzione QualifierSet_Get (riferimenti alle API non gestite)
description: La funzione QualifierSet_Get Ottiene un qualificatore denominato.
ms.date: 11/06/2017
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
ms.openlocfilehash: e8c10a680f1caffd583097b16c046729fe10b140
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804240"
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="c4fa7-103">QualifierSet_Get (funzione)</span><span class="sxs-lookup"><span data-stu-id="c4fa7-103">QualifierSet_Get function</span></span>
<span data-ttu-id="c4fa7-104">Ottiene il qualificatore denominato specificato.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c4fa7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4fa7-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="c4fa7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c4fa7-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="c4fa7-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="c4fa7-108">[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="c4fa7-109">[in] Il nome del qualificatore il cui valore viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="c4fa7-110">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-110">[in] Reserved.</span></span> <span data-ttu-id="c4fa7-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="c4fa7-112">[out] Al termine, il tipo corretto e il valore del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="c4fa7-113">Se la funzione ha esito negativo, il `VARIANT` a cui punta `pVal` non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="c4fa7-114">Se questo parametro è `null`, il parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="c4fa7-115">[out] Puntatore a un valore LONG che riceve i bit flavor qualificatore per il qualificatore richiesto.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="c4fa7-116">Se non si desiderano informazioni di versione, questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="c4fa7-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c4fa7-117">Return value</span></span>

<span data-ttu-id="c4fa7-118">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="c4fa7-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c4fa7-119">Costante</span><span class="sxs-lookup"><span data-stu-id="c4fa7-119">Constant</span></span>  |<span data-ttu-id="c4fa7-120">Valore</span><span class="sxs-lookup"><span data-stu-id="c4fa7-120">Value</span></span>  |<span data-ttu-id="c4fa7-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4fa7-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c4fa7-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c4fa7-122">0x80041008</span></span> | <span data-ttu-id="c4fa7-123">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c4fa7-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c4fa7-124">0x80041002</span></span> | <span data-ttu-id="c4fa7-125">Il qualificatore specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c4fa7-126">0</span><span class="sxs-lookup"><span data-stu-id="c4fa7-126">0</span></span> | <span data-ttu-id="c4fa7-127">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c4fa7-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c4fa7-128">Note</span><span class="sxs-lookup"><span data-stu-id="c4fa7-128">Remarks</span></span>

<span data-ttu-id="c4fa7-129">Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c4fa7-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4fa7-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4fa7-130">Requirements</span></span>  
 <span data-ttu-id="c4fa7-131">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4fa7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4fa7-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c4fa7-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c4fa7-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c4fa7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fa7-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4fa7-134">See also</span></span>  
[<span data-ttu-id="c4fa7-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c4fa7-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
