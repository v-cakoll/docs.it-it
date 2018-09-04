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
ms.openlocfilehash: d1cc754fcf7d1defa815bb0a74b7c2b4a6909478
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539328"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="66d13-103">GetMethodOrigin (funzione)</span><span class="sxs-lookup"><span data-stu-id="66d13-103">GetMethodOrigin function</span></span>
<span data-ttu-id="66d13-104">Determina la classe in cui viene dichiarato un metodo.</span><span class="sxs-lookup"><span data-stu-id="66d13-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="66d13-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66d13-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="66d13-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="66d13-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="66d13-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="66d13-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="66d13-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="66d13-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="66d13-109">[in] Il nome del metodo per l'oggetto la cui classe proprietaria è richiesto.</span><span class="sxs-lookup"><span data-stu-id="66d13-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="66d13-110">[out] Riceve il nome della classe cui appartiene il metodo.</span><span class="sxs-lookup"><span data-stu-id="66d13-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="66d13-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="66d13-111">Return value</span></span>

<span data-ttu-id="66d13-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="66d13-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="66d13-113">Costante</span><span class="sxs-lookup"><span data-stu-id="66d13-113">Constant</span></span>  |<span data-ttu-id="66d13-114">Valore</span><span class="sxs-lookup"><span data-stu-id="66d13-114">Value</span></span>  |<span data-ttu-id="66d13-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66d13-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="66d13-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="66d13-116">0x80041002</span></span> | <span data-ttu-id="66d13-117">Il metodo specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="66d13-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="66d13-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="66d13-118">0x80041008</span></span> | <span data-ttu-id="66d13-119">Uno o più parametri non vengono.</span><span class="sxs-lookup"><span data-stu-id="66d13-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="66d13-120">0</span><span class="sxs-lookup"><span data-stu-id="66d13-120">0</span></span> | <span data-ttu-id="66d13-121">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="66d13-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="66d13-122">Note</span><span class="sxs-lookup"><span data-stu-id="66d13-122">Remarks</span></span>

<span data-ttu-id="66d13-123">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="66d13-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="66d13-124">Poiché una classe può ereditare i metodi da una o più classi base, gli sviluppatori spesso vogliono determinare la classe in cui è definito un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="66d13-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="66d13-125">Il `pstrClassName` parametro non deve puntare a un valore valido `BSTR` prima di chiamare la funzione poiché si tratta di un `out` parametro; questo puntatore non viene deallocato dopo la funzione restituisce.</span><span class="sxs-lookup"><span data-stu-id="66d13-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="66d13-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66d13-126">Requirements</span></span>  
<span data-ttu-id="66d13-127">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66d13-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d13-128">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="66d13-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="66d13-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="66d13-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d13-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66d13-130">See also</span></span>  
[<span data-ttu-id="66d13-131">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="66d13-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
