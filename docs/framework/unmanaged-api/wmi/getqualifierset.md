---
title: Funzione GetQualifierSet (riferimenti alle API non gestite)
description: La funzione GetQualifierSet recupera il qualificatore impostato per una classe o un'istanza.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176773"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="1aa13-103">Funzione GetQualifierSet</span><span class="sxs-lookup"><span data-stu-id="1aa13-103">GetQualifierSet function</span></span>
<span data-ttu-id="1aa13-104">Recupera il qualificatore impostato per l'istanza di una classe o la definizione di una classe.</span><span class="sxs-lookup"><span data-stu-id="1aa13-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1aa13-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1aa13-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="1aa13-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1aa13-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1aa13-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1aa13-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1aa13-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="1aa13-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="1aa13-109">[fuori] Riceve il puntatore a interfaccia che consente l'accesso ai qualificatori dell'oggetto classe.</span><span class="sxs-lookup"><span data-stu-id="1aa13-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="1aa13-110">Il parametro `ppQualSet` non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="1aa13-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="1aa13-111">Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="1aa13-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="1aa13-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1aa13-112">Return value</span></span>

<span data-ttu-id="1aa13-113">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="1aa13-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1aa13-114">Costante</span><span class="sxs-lookup"><span data-stu-id="1aa13-114">Constant</span></span>  |<span data-ttu-id="1aa13-115">valore</span><span class="sxs-lookup"><span data-stu-id="1aa13-115">Value</span></span>  |<span data-ttu-id="1aa13-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1aa13-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="1aa13-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1aa13-117">0x80041001</span></span> | <span data-ttu-id="1aa13-118">C'è stato un fallimento generale.</span><span class="sxs-lookup"><span data-stu-id="1aa13-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="1aa13-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1aa13-119">0x80041002</span></span> | <span data-ttu-id="1aa13-120">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="1aa13-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1aa13-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1aa13-121">0x80041006</span></span> | <span data-ttu-id="1aa13-122">Memoria insufficiente per completare l’operazione.</span><span class="sxs-lookup"><span data-stu-id="1aa13-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1aa13-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1aa13-123">0x80041008</span></span> | <span data-ttu-id="1aa13-124">Un parametro è `null`.</span><span class="sxs-lookup"><span data-stu-id="1aa13-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1aa13-125">0</span><span class="sxs-lookup"><span data-stu-id="1aa13-125">0</span></span> | <span data-ttu-id="1aa13-126">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1aa13-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1aa13-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1aa13-127">Remarks</span></span>

<span data-ttu-id="1aa13-128">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="1aa13-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="1aa13-129">Il [puntatore IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.</span><span class="sxs-lookup"><span data-stu-id="1aa13-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="1aa13-130">Tali qualificatori aggiunti, modificati o eliminati si applicano all'intera definizione di istanza o classe.</span><span class="sxs-lookup"><span data-stu-id="1aa13-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="1aa13-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1aa13-131">Requirements</span></span>  
<span data-ttu-id="1aa13-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aa13-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa13-133">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1aa13-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1aa13-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1aa13-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa13-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aa13-135">See also</span></span>

- [<span data-ttu-id="1aa13-136">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1aa13-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
