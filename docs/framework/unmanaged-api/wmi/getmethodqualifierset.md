---
title: Funzione GetMethodQualifierSet (riferimenti alle API non gestite)
description: La funzione GetMethodQualifierSet recupera set di qualificatore del metodo.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a363591f5db7a2dbcba1147df35d8c023c9b0707
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332112"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="c450b-103">GetMethodQualifierSet (funzione)</span><span class="sxs-lookup"><span data-stu-id="c450b-103">GetMethodQualifierSet function</span></span>
<span data-ttu-id="c450b-104">Recupera il qualificatore impostato per un particolare metodo.</span><span class="sxs-lookup"><span data-stu-id="c450b-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c450b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c450b-105">Syntax</span></span>  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="c450b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c450b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c450b-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="c450b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c450b-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="c450b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`  
<span data-ttu-id="c450b-109">[in] Il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="c450b-109">[in] The method  name.</span></span> <span data-ttu-id="c450b-110">`wszMethod` deve puntare a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="c450b-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="c450b-111">[out] Riceve il puntatore a interfaccia che consente l'accesso per i qualificatori del metodo.</span><span class="sxs-lookup"><span data-stu-id="c450b-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="c450b-112">Il parametro `ppQualSet` non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="c450b-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="c450b-113">Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore viene impostato in modo che punti a `null`.</span><span class="sxs-lookup"><span data-stu-id="c450b-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="c450b-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c450b-114">Return value</span></span>

<span data-ttu-id="c450b-115">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="c450b-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c450b-116">Costante</span><span class="sxs-lookup"><span data-stu-id="c450b-116">Constant</span></span>  |<span data-ttu-id="c450b-117">Valore</span><span class="sxs-lookup"><span data-stu-id="c450b-117">Value</span></span>  |<span data-ttu-id="c450b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c450b-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c450b-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c450b-119">0x80041002</span></span> | <span data-ttu-id="c450b-120">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="c450b-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c450b-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c450b-121">0x80041008</span></span> | <span data-ttu-id="c450b-122">È un parametro `null`.</span><span class="sxs-lookup"><span data-stu-id="c450b-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c450b-123">0</span><span class="sxs-lookup"><span data-stu-id="c450b-123">0</span></span> | <span data-ttu-id="c450b-124">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c450b-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c450b-125">Note</span><span class="sxs-lookup"><span data-stu-id="c450b-125">Remarks</span></span>

<span data-ttu-id="c450b-126">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c450b-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span> 

<span data-ttu-id="c450b-127">Una chiamata a questa funzione è supportata solo se l'oggetto corrente è una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="c450b-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="c450b-128">Manipolazione di metodo non è disponibile per [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="c450b-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters that point to CIM instances.</span></span>

<span data-ttu-id="c450b-129">Poiché ogni metodo può avere un proprio qualificatori, il [puntatore IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.</span><span class="sxs-lookup"><span data-stu-id="c450b-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="c450b-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c450b-130">Requirements</span></span>  
<span data-ttu-id="c450b-131">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c450b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c450b-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c450b-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c450b-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c450b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c450b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c450b-134">See also</span></span>  
[<span data-ttu-id="c450b-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c450b-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
