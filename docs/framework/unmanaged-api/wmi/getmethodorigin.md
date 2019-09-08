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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cea7251353dae093f64448c8d84157917fa74c5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798553"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="7def4-103">Funzione GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="7def4-103">GetMethodOrigin function</span></span>
<span data-ttu-id="7def4-104">Determina la classe in cui viene dichiarato un metodo.</span><span class="sxs-lookup"><span data-stu-id="7def4-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="7def4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7def4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="7def4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7def4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7def4-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="7def4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7def4-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="7def4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="7def4-109">in Nome del metodo per l'oggetto di cui viene richiesta la classe proprietaria.</span><span class="sxs-lookup"><span data-stu-id="7def4-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="7def4-110">out Riceve il nome della classe a cui appartiene il metodo.</span><span class="sxs-lookup"><span data-stu-id="7def4-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="7def4-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7def4-111">Return value</span></span>

<span data-ttu-id="7def4-112">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="7def4-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7def4-113">Costante</span><span class="sxs-lookup"><span data-stu-id="7def4-113">Constant</span></span>  |<span data-ttu-id="7def4-114">Valore</span><span class="sxs-lookup"><span data-stu-id="7def4-114">Value</span></span>  |<span data-ttu-id="7def4-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7def4-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="7def4-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7def4-116">0x80041002</span></span> | <span data-ttu-id="7def4-117">Il metodo specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="7def4-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7def4-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7def4-118">0x80041008</span></span> | <span data-ttu-id="7def4-119">Uno o più parametri non sono validi.</span><span class="sxs-lookup"><span data-stu-id="7def4-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7def4-120">0</span><span class="sxs-lookup"><span data-stu-id="7def4-120">0</span></span> | <span data-ttu-id="7def4-121">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="7def4-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7def4-122">Note</span><span class="sxs-lookup"><span data-stu-id="7def4-122">Remarks</span></span>

<span data-ttu-id="7def4-123">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .</span><span class="sxs-lookup"><span data-stu-id="7def4-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="7def4-124">Poiché una classe può ereditare metodi da una o più classi base, gli sviluppatori spesso vogliono determinare la classe in cui è definito un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="7def4-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="7def4-125">Il `pstrClassName` parametro non deve puntare a un oggetto `BSTR` valido prima che la funzione venga chiamata perché si `out` tratta di un parametro; questo puntatore non viene deallocato dopo la restituzione della funzione.</span><span class="sxs-lookup"><span data-stu-id="7def4-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="7def4-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7def4-126">Requirements</span></span>  
<span data-ttu-id="7def4-127">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7def4-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7def4-128">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="7def4-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7def4-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7def4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7def4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7def4-130">See also</span></span>

- [<span data-ttu-id="7def4-131">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="7def4-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
