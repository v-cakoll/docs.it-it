---
title: 'IMetaDataImport:: GetMethod (funzione) (riferimenti alle API non gestite)'
description: La funzione GetMethod recupera informazioni su un metodo.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a405c5e245558e6b8d1b389bfc143faae4550a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577594"
---
# <a name="getmethod-function"></a><span data-ttu-id="16b1d-103">GetMethod (funzione)</span><span class="sxs-lookup"><span data-stu-id="16b1d-103">GetMethod function</span></span>
<span data-ttu-id="16b1d-104">Recupera le informazioni relative al metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="16b1d-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="16b1d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16b1d-105">Syntax</span></span>  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="16b1d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="16b1d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="16b1d-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="16b1d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="16b1d-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="16b1d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="16b1d-109">[in] Il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="16b1d-109">[in] The method name.</span></span> <span data-ttu-id="16b1d-110">Questo parametro non può essere `null` e deve puntare a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="16b1d-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="16b1d-111">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="16b1d-111">[in] Reserved.</span></span> <span data-ttu-id="16b1d-112">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="16b1d-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="16b1d-113">[out] Un puntatore all'indirizzo di un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza che descrive il paramteers al metodo.</span><span class="sxs-lookup"><span data-stu-id="16b1d-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="16b1d-114">Questo parametro viene ignorato se è impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="16b1d-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="16b1d-115">[out] Un puntatore all'indirizzo di un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza che descrive i parametri out al metodo.</span><span class="sxs-lookup"><span data-stu-id="16b1d-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="16b1d-116">Questo parametro viene ignorato se è impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="16b1d-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="16b1d-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="16b1d-117">Return value</span></span>

<span data-ttu-id="16b1d-118">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="16b1d-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="16b1d-119">Costante</span><span class="sxs-lookup"><span data-stu-id="16b1d-119">Constant</span></span>  |<span data-ttu-id="16b1d-120">Value</span><span class="sxs-lookup"><span data-stu-id="16b1d-120">Value</span></span>  |<span data-ttu-id="16b1d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16b1d-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="16b1d-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="16b1d-122">0x80041002</span></span> | <span data-ttu-id="16b1d-123">La proprietà specificata non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="16b1d-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="16b1d-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="16b1d-124">0x80041006</span></span> | <span data-ttu-id="16b1d-125">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="16b1d-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="16b1d-126">0</span><span class="sxs-lookup"><span data-stu-id="16b1d-126">0</span></span> | <span data-ttu-id="16b1d-127">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="16b1d-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="16b1d-128">Note</span><span class="sxs-lookup"><span data-stu-id="16b1d-128">Remarks</span></span>

<span data-ttu-id="16b1d-129">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="16b1d-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="16b1d-130">Gestione di Windows è possibile impostare il [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatore a `null` se il metodo ha alcun parametro in.</span><span class="sxs-lookup"><span data-stu-id="16b1d-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="16b1d-131">Nelle `ppInSignature` e `ppOutSignature` descrivono in e out parametri, rispettivamente, come proprietà in un `IWbemClassObject` istanza della classe di sistema [parametry](/windows/desktop/WmiSdk/--parameters).</span><span class="sxs-lookup"><span data-stu-id="16b1d-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="16b1d-132">Le proprietà nella `ppInsignature` sono denominati `Param` *n*, dove *n* è la posizione del parametro nella firma del metodo (ad esempio `Param1`, `Param2`e così via.).</span><span class="sxs-lookup"><span data-stu-id="16b1d-132">The properties in `ppInsignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="16b1d-133">Le proprietà nella `ppOutSignature` sono denominate anche `Param` *n*, e il valore restituito è denominato `ReturnValue`.</span><span class="sxs-lookup"><span data-stu-id="16b1d-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="16b1d-134">Per altre informazioni e un esempio, vedere [IWbemClassObject::GetMethod metodo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span><span class="sxs-lookup"><span data-stu-id="16b1d-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="16b1d-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16b1d-135">Requirements</span></span>  
<span data-ttu-id="16b1d-136">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16b1d-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b1d-137">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="16b1d-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="16b1d-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="16b1d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b1d-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16b1d-139">See also</span></span>
- [<span data-ttu-id="16b1d-140">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="16b1d-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
