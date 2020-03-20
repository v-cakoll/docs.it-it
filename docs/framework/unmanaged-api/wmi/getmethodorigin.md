---
title: Funzione GetMethodOrigin (riferimenti alle API non gestite)
description: La funzione GetMethodOrigin determina la classe in cui viene dichiarato un metodo.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b4609b6649be875aea7dfcf52ba36b1e98ab7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176799"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="a3691-103">Funzione GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="a3691-103">GetMethodOrigin function</span></span>
<span data-ttu-id="a3691-104">Determina la classe in cui viene dichiarato un metodo.</span><span class="sxs-lookup"><span data-stu-id="a3691-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a3691-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3691-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```  

## <a name="parameters"></a><span data-ttu-id="a3691-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3691-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a3691-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a3691-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a3691-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="a3691-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="a3691-109">[in] Nome del metodo per l'oggetto di cui viene richiesta la classe proprietaria.</span><span class="sxs-lookup"><span data-stu-id="a3691-109">[in] The name of the method for the object whose owning class is being requested.</span></span>

`pstrClassName`  
<span data-ttu-id="a3691-110">[fuori] Riceve il nome della classe proprietaria del metodo.</span><span class="sxs-lookup"><span data-stu-id="a3691-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="a3691-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a3691-111">Return value</span></span>

<span data-ttu-id="a3691-112">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="a3691-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a3691-113">Costante</span><span class="sxs-lookup"><span data-stu-id="a3691-113">Constant</span></span>  |<span data-ttu-id="a3691-114">valore</span><span class="sxs-lookup"><span data-stu-id="a3691-114">Value</span></span>  |<span data-ttu-id="a3691-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3691-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a3691-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a3691-116">0x80041002</span></span> | <span data-ttu-id="a3691-117">Il metodo specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="a3691-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a3691-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a3691-118">0x80041008</span></span> | <span data-ttu-id="a3691-119">Uno o più parametri non sono validi.</span><span class="sxs-lookup"><span data-stu-id="a3691-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a3691-120">0</span><span class="sxs-lookup"><span data-stu-id="a3691-120">0</span></span> | <span data-ttu-id="a3691-121">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a3691-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a3691-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a3691-122">Remarks</span></span>

<span data-ttu-id="a3691-123">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .</span><span class="sxs-lookup"><span data-stu-id="a3691-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="a3691-124">Poiché una classe può ereditare metodi da una o più classi base, gli sviluppatori spesso desiderano determinare la classe in cui è definito un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="a3691-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="a3691-125">Il `pstrClassName` parametro non deve `BSTR` puntare a un valido `out` prima che la funzione viene chiamata perché si tratta di un parametro. questo puntatore non viene deallocato dopo la restituzione della funzione.</span><span class="sxs-lookup"><span data-stu-id="a3691-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="a3691-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3691-126">Requirements</span></span>  
<span data-ttu-id="a3691-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3691-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3691-128">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a3691-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a3691-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a3691-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3691-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3691-130">See also</span></span>

- [<span data-ttu-id="a3691-131">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="a3691-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
