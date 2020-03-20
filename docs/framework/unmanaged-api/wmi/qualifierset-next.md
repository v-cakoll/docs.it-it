---
title: QualifierSet_Next function (Unmanaged API Reference)
description: La funzione QualifierSet_Next recupera il qualificatore successivo in un'enumerazione.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174875"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="a23dd-103">Funzione QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="a23dd-103">QualifierSet_Next function</span></span>
<span data-ttu-id="a23dd-104">Recupera il qualificatore successivo in un'enumerazione avviata con una chiamata alla funzione [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="a23dd-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a23dd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a23dd-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="a23dd-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a23dd-106">Parameters</span></span>

<span data-ttu-id="a23dd-107">`vFunc`[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a23dd-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="a23dd-108">`ptr`[in] Puntatore a [un'istanza di IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="a23dd-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="a23dd-109">`lFlags`[in] Riservati.</span><span class="sxs-lookup"><span data-stu-id="a23dd-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="a23dd-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="a23dd-110">This parameter must be 0.</span></span>

<span data-ttu-id="a23dd-111">`pstrName`[fuori] Nome del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="a23dd-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="a23dd-112">Se `null`, questo parametro viene ignorato; in `pstrName` caso contrario, `BSTR` non deve puntare a un valore valido o si verifica una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="a23dd-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="a23dd-113">Se non è null, la `BSTR` funzione alloca sempre un nuovo quando restituisce `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="a23dd-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="a23dd-114">`pVal`[fuori] In caso di esito positivo, valore per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="a23dd-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="a23dd-115">Se la funzione `VARIANT` ha esito negativo, l'oggetto indicato da `pVal` non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="a23dd-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="a23dd-116">Se questo `null`parametro è , il parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="a23dd-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="a23dd-117">`plFlavor`[fuori] Puntatore a un long che riceve il sapore del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="a23dd-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="a23dd-118">Se le informazioni sul sapore non `null`sono desiderate, questo parametro può essere .</span><span class="sxs-lookup"><span data-stu-id="a23dd-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a23dd-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a23dd-119">Return value</span></span>

<span data-ttu-id="a23dd-120">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="a23dd-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a23dd-121">Costante</span><span class="sxs-lookup"><span data-stu-id="a23dd-121">Constant</span></span>  |<span data-ttu-id="a23dd-122">valore</span><span class="sxs-lookup"><span data-stu-id="a23dd-122">Value</span></span>  |<span data-ttu-id="a23dd-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a23dd-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a23dd-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a23dd-124">0x80041008</span></span> | <span data-ttu-id="a23dd-125">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="a23dd-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="a23dd-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="a23dd-126">0x8004101d</span></span> | <span data-ttu-id="a23dd-127">Il chiamante non ha chiamato [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="a23dd-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a23dd-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a23dd-128">0x80041006</span></span> | <span data-ttu-id="a23dd-129">Memoria insufficiente per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a23dd-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="a23dd-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="a23dd-130">0x40005</span></span> | <span data-ttu-id="a23dd-131">Non sono rimasti altri qualificatori nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a23dd-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a23dd-132">0</span><span class="sxs-lookup"><span data-stu-id="a23dd-132">0</span></span> | <span data-ttu-id="a23dd-133">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a23dd-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a23dd-134">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a23dd-134">Remarks</span></span>

<span data-ttu-id="a23dd-135">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemQualifierSet::Next.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)</span><span class="sxs-lookup"><span data-stu-id="a23dd-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="a23dd-136">Chiamare la `QualifierSet_Next` funzione ripetutamente per enumerare tutti `WBEM_S_NO_MORE_DATA`i qualificatori fino a quando la funzione restituisce .</span><span class="sxs-lookup"><span data-stu-id="a23dd-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="a23dd-137">Per terminare l'enumerazione in anticipo, chiamare la funzione [QualifierSet_EndEnumeration.](qualifierset-endenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="a23dd-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="a23dd-138">L'ordine dei qualificatori restituiti durante l'enumerazione non è definito.</span><span class="sxs-lookup"><span data-stu-id="a23dd-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="a23dd-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a23dd-139">Requirements</span></span>  
 <span data-ttu-id="a23dd-140">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a23dd-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a23dd-141">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a23dd-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a23dd-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a23dd-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23dd-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a23dd-143">See also</span></span>

- [<span data-ttu-id="a23dd-144">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="a23dd-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
