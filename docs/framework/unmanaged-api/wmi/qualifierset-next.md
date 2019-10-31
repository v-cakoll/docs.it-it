---
title: Funzione QualifierSet_Next (riferimenti alle API non gestite)
description: La funzione QualifierSet_Next Recupera il qualificatore successivo in un'enumerazione.
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
ms.openlocfilehash: c9c824b0158618848c13183d92f88604460d5099
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141719"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="6c2b5-103">QualifierSet_Next (funzione)</span><span class="sxs-lookup"><span data-stu-id="6c2b5-103">QualifierSet_Next function</span></span>
<span data-ttu-id="6c2b5-104">Recupera il qualificatore successivo in un'enumerazione avviata con una chiamata alla funzione [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6c2b5-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6c2b5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c2b5-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="6c2b5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c2b5-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="6c2b5-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="6c2b5-108">in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="6c2b5-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="6c2b5-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-109">[in] Reserved.</span></span> <span data-ttu-id="6c2b5-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="6c2b5-111">out Nome del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="6c2b5-112">Se `null`, questo parametro viene ignorato; in caso contrario, `pstrName` non deve puntare a una `BSTR` valida o si verifica una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="6c2b5-113">Se non è null, la funzione alloca sempre un nuovo `BSTR` quando restituisce `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="6c2b5-114">out In caso di esito positivo, il valore per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="6c2b5-115">Se la funzione ha esito negativo, il `VARIANT` a cui punta `pVal` non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="6c2b5-116">Se questo parametro è `null`, il parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="6c2b5-117">out Puntatore a un oggetto LONG che riceve la versione del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="6c2b5-118">Se non si desidera ottenere informazioni sul sapore, questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="6c2b5-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c2b5-119">Return value</span></span>

<span data-ttu-id="6c2b5-120">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="6c2b5-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6c2b5-121">Costante</span><span class="sxs-lookup"><span data-stu-id="6c2b5-121">Constant</span></span>  |<span data-ttu-id="6c2b5-122">Value</span><span class="sxs-lookup"><span data-stu-id="6c2b5-122">Value</span></span>  |<span data-ttu-id="6c2b5-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c2b5-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6c2b5-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6c2b5-124">0x80041008</span></span> | <span data-ttu-id="6c2b5-125">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="6c2b5-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="6c2b5-126">0x8004101d</span></span> | <span data-ttu-id="6c2b5-127">Il chiamante non ha chiamato [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6c2b5-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6c2b5-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6c2b5-128">0x80041006</span></span> | <span data-ttu-id="6c2b5-129">La memoria disponibile non è sufficiente per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="6c2b5-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="6c2b5-130">0x40005</span></span> | <span data-ttu-id="6c2b5-131">Nessun qualificatore rimanente nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6c2b5-132">0</span><span class="sxs-lookup"><span data-stu-id="6c2b5-132">0</span></span> | <span data-ttu-id="6c2b5-133">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6c2b5-134">Note</span><span class="sxs-lookup"><span data-stu-id="6c2b5-134">Remarks</span></span>

<span data-ttu-id="6c2b5-135">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .</span><span class="sxs-lookup"><span data-stu-id="6c2b5-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="6c2b5-136">Chiamare ripetutamente la funzione `QualifierSet_Next` per enumerare tutti i qualificatori fino a quando la funzione non restituisce `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="6c2b5-137">Per terminare l'enumerazione in anticipo, chiamare la funzione [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6c2b5-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="6c2b5-138">L'ordine dei qualificatori restituiti durante l'enumerazione non è definito.</span><span class="sxs-lookup"><span data-stu-id="6c2b5-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c2b5-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c2b5-139">Requirements</span></span>  
 <span data-ttu-id="6c2b5-140">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c2b5-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c2b5-141">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="6c2b5-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6c2b5-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c2b5-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2b5-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c2b5-143">See also</span></span>

- [<span data-ttu-id="6c2b5-144">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="6c2b5-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
