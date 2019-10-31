---
title: Funzione GetMethodQualifierSet (riferimenti alle API non gestite)
description: La funzione GetMethodQualifierSet Recupera il set di qualificatori di un metodo.
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
ms.openlocfilehash: 1a36200fd214d013a10ed21c22e1f652de2cbf17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102580"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="1900d-103">Funzione GetMethodQualifierSet</span><span class="sxs-lookup"><span data-stu-id="1900d-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="1900d-104">Recupera il qualificatore impostato per un particolare metodo.</span><span class="sxs-lookup"><span data-stu-id="1900d-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1900d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1900d-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="1900d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1900d-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="1900d-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="1900d-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="1900d-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="1900d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="1900d-109">in Nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="1900d-109">[in] The method  name.</span></span> <span data-ttu-id="1900d-110">`wszMethod` deve puntare a una `LPCWSTR`valida.</span><span class="sxs-lookup"><span data-stu-id="1900d-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="1900d-111">out Riceve il puntatore a interfaccia che consente di accedere ai qualificatori del metodo.</span><span class="sxs-lookup"><span data-stu-id="1900d-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="1900d-112">Il parametro `ppQualSet` non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="1900d-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="1900d-113">Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore è impostato in modo da puntare a `null`.</span><span class="sxs-lookup"><span data-stu-id="1900d-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="1900d-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1900d-114">Return value</span></span>

<span data-ttu-id="1900d-115">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="1900d-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1900d-116">Costante</span><span class="sxs-lookup"><span data-stu-id="1900d-116">Constant</span></span>  |<span data-ttu-id="1900d-117">Value</span><span class="sxs-lookup"><span data-stu-id="1900d-117">Value</span></span>  |<span data-ttu-id="1900d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1900d-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="1900d-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1900d-119">0x80041002</span></span> | <span data-ttu-id="1900d-120">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="1900d-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1900d-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1900d-121">0x80041008</span></span> | <span data-ttu-id="1900d-122">Un parametro è `null`.</span><span class="sxs-lookup"><span data-stu-id="1900d-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1900d-123">0</span><span class="sxs-lookup"><span data-stu-id="1900d-123">0</span></span> | <span data-ttu-id="1900d-124">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1900d-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="1900d-125">Note</span><span class="sxs-lookup"><span data-stu-id="1900d-125">Remarks</span></span>

<span data-ttu-id="1900d-126">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="1900d-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="1900d-127">Una chiamata a questa funzione è supportata solo se l'oggetto corrente è una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="1900d-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="1900d-128">La manipolazione del metodo non è disponibile per i puntatori [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="1900d-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="1900d-129">Poiché ogni metodo può avere qualificatori propri, il [puntatore IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.</span><span class="sxs-lookup"><span data-stu-id="1900d-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="1900d-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1900d-130">Requirements</span></span>

<span data-ttu-id="1900d-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1900d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="1900d-132">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="1900d-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="1900d-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1900d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1900d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1900d-134">See also</span></span>

- [<span data-ttu-id="1900d-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1900d-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
