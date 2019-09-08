---
title: Funzione QualifierSet_Get (riferimenti alle API non gestite)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 751694985248346187eff016ef7a4a8054cb1212
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798307"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="1c4c9-103">QualifierSet_Get (funzione)</span><span class="sxs-lookup"><span data-stu-id="1c4c9-103">QualifierSet_Get function</span></span>
<span data-ttu-id="1c4c9-104">Ottiene il qualificatore denominato specificato.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1c4c9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c4c9-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="1c4c9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c4c9-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="1c4c9-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="1c4c9-108">in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="1c4c9-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="1c4c9-109">in Nome del qualificatore il cui valore è richiesto.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="1c4c9-110">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-110">[in] Reserved.</span></span> <span data-ttu-id="1c4c9-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="1c4c9-112">out In caso di esito positivo, il tipo e il valore corretti per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="1c4c9-113">Se la funzione `pVal` ha esito `VARIANT` negativo, l'oggetto a cui fa riferimento non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="1c4c9-114">Se questo parametro è `null`, il parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="1c4c9-115">out Puntatore a un oggetto LONG che riceve i bit di sapore del qualificatore per il qualificatore richiesto.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="1c4c9-116">Se non si desidera ottenere informazioni sul sapore, questo parametro `null`può essere.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="1c4c9-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1c4c9-117">Return value</span></span>

<span data-ttu-id="1c4c9-118">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="1c4c9-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1c4c9-119">Costante</span><span class="sxs-lookup"><span data-stu-id="1c4c9-119">Constant</span></span>  |<span data-ttu-id="1c4c9-120">Valore</span><span class="sxs-lookup"><span data-stu-id="1c4c9-120">Value</span></span>  |<span data-ttu-id="1c4c9-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1c4c9-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1c4c9-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1c4c9-122">0x80041008</span></span> | <span data-ttu-id="1c4c9-123">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="1c4c9-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1c4c9-124">0x80041002</span></span> | <span data-ttu-id="1c4c9-125">Il qualificatore specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1c4c9-126">0</span><span class="sxs-lookup"><span data-stu-id="1c4c9-126">0</span></span> | <span data-ttu-id="1c4c9-127">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1c4c9-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1c4c9-128">Note</span><span class="sxs-lookup"><span data-stu-id="1c4c9-128">Remarks</span></span>

<span data-ttu-id="1c4c9-129">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) .</span><span class="sxs-lookup"><span data-stu-id="1c4c9-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c4c9-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c4c9-130">Requirements</span></span>  
 <span data-ttu-id="1c4c9-131">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c4c9-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c4c9-132">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="1c4c9-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1c4c9-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1c4c9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4c9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c4c9-134">See also</span></span>

- [<span data-ttu-id="1c4c9-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1c4c9-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
