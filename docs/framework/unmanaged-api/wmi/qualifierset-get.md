---
title: QualifierSet_Get function (Unmanaged API Reference)
description: La funzione QualifierSet_Get ottiene un qualificatore denominato.
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
ms.openlocfilehash: 2f4e2d4518e01f3415b8f17ce5778dd98b2a45c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174888"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="59cc4-103">Funzione QualifierSet_Get</span><span class="sxs-lookup"><span data-stu-id="59cc4-103">QualifierSet_Get function</span></span>
<span data-ttu-id="59cc4-104">Ottiene il qualificatore denominato specificato.</span><span class="sxs-lookup"><span data-stu-id="59cc4-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="59cc4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59cc4-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="59cc4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="59cc4-106">Parameters</span></span>

<span data-ttu-id="59cc4-107">`vFunc`[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="59cc4-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="59cc4-108">`ptr`[in] Puntatore a [un'istanza di IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="59cc4-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="59cc4-109">`wszName`[in] Nome del qualificatore il cui valore è richiesto.</span><span class="sxs-lookup"><span data-stu-id="59cc4-109">`wszName` [in] The name of the qualifier whose value is requested.</span></span>

<span data-ttu-id="59cc4-110">`lFlags`[in] Riservati.</span><span class="sxs-lookup"><span data-stu-id="59cc4-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="59cc4-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="59cc4-111">This parameter must be 0.</span></span>

<span data-ttu-id="59cc4-112">`pVal`[fuori] In caso di esito positivo, il tipo e il valore corretti per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="59cc4-112">`pVal` [out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="59cc4-113">Se la funzione `VARIANT` ha esito negativo, l'oggetto indicato da `pVal` non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="59cc4-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="59cc4-114">Se questo `null`parametro è , il parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="59cc4-114">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="59cc4-115">`plFlavor`[fuori] Puntatore a un oggetto LONG che riceve i bit di tipo gusto del qualificatore per il qualificatore richiesto.</span><span class="sxs-lookup"><span data-stu-id="59cc4-115">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="59cc4-116">Se le informazioni sul sapore non `null`sono desiderate, questo parametro può essere .</span><span class="sxs-lookup"><span data-stu-id="59cc4-116">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="59cc4-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="59cc4-117">Return value</span></span>

<span data-ttu-id="59cc4-118">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="59cc4-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="59cc4-119">Costante</span><span class="sxs-lookup"><span data-stu-id="59cc4-119">Constant</span></span>  |<span data-ttu-id="59cc4-120">valore</span><span class="sxs-lookup"><span data-stu-id="59cc4-120">Value</span></span>  |<span data-ttu-id="59cc4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59cc4-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="59cc4-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="59cc4-122">0x80041008</span></span> | <span data-ttu-id="59cc4-123">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="59cc4-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="59cc4-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="59cc4-124">0x80041002</span></span> | <span data-ttu-id="59cc4-125">Il qualificatore specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="59cc4-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="59cc4-126">0</span><span class="sxs-lookup"><span data-stu-id="59cc4-126">0</span></span> | <span data-ttu-id="59cc4-127">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="59cc4-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="59cc4-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="59cc4-128">Remarks</span></span>

<span data-ttu-id="59cc4-129">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemQualifierSet::Get.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)</span><span class="sxs-lookup"><span data-stu-id="59cc4-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="59cc4-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59cc4-130">Requirements</span></span>  
 <span data-ttu-id="59cc4-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59cc4-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59cc4-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="59cc4-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="59cc4-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59cc4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59cc4-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59cc4-134">See also</span></span>

- [<span data-ttu-id="59cc4-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="59cc4-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
