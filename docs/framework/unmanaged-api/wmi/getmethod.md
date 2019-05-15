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
ms.openlocfilehash: 419fb33155cfa91199e52110da29efd44d606f4b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636602"
---
# <a name="getmethod-function"></a><span data-ttu-id="a47b6-103">Funzione GetMethod</span><span class="sxs-lookup"><span data-stu-id="a47b6-103">GetMethod function</span></span>

<span data-ttu-id="a47b6-104">Recupera le informazioni relative al metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="a47b6-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a47b6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a47b6-105">Syntax</span></span>

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a><span data-ttu-id="a47b6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a47b6-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="a47b6-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="a47b6-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="a47b6-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="a47b6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="a47b6-109">[in] Il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="a47b6-109">[in] The method name.</span></span> <span data-ttu-id="a47b6-110">Questo parametro non può essere `null` e deve puntare a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="a47b6-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="a47b6-111">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="a47b6-111">[in] Reserved.</span></span> <span data-ttu-id="a47b6-112">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="a47b6-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="a47b6-113">[out] Un puntatore all'indirizzo di un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza che descrive i parametri in al metodo.</span><span class="sxs-lookup"><span data-stu-id="a47b6-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="a47b6-114">Questo parametro viene ignorato se è impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="a47b6-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="a47b6-115">[out] Un puntatore all'indirizzo di un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza che descrive i parametri out al metodo.</span><span class="sxs-lookup"><span data-stu-id="a47b6-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="a47b6-116">Questo parametro viene ignorato se è impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="a47b6-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a47b6-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a47b6-117">Return value</span></span>

<span data-ttu-id="a47b6-118">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="a47b6-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a47b6-119">Costante</span><span class="sxs-lookup"><span data-stu-id="a47b6-119">Constant</span></span>  |<span data-ttu-id="a47b6-120">Value</span><span class="sxs-lookup"><span data-stu-id="a47b6-120">Value</span></span>  |<span data-ttu-id="a47b6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a47b6-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a47b6-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a47b6-122">0x80041002</span></span> | <span data-ttu-id="a47b6-123">La proprietà specificata non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="a47b6-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a47b6-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a47b6-124">0x80041006</span></span> | <span data-ttu-id="a47b6-125">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a47b6-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a47b6-126">0</span><span class="sxs-lookup"><span data-stu-id="a47b6-126">0</span></span> | <span data-ttu-id="a47b6-127">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a47b6-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="a47b6-128">Note</span><span class="sxs-lookup"><span data-stu-id="a47b6-128">Remarks</span></span>

<span data-ttu-id="a47b6-129">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="a47b6-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="a47b6-130">Gestione di Windows è possibile impostare il [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatore a `null` se il metodo ha alcun parametro in.</span><span class="sxs-lookup"><span data-stu-id="a47b6-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="a47b6-131">Nelle `ppInSignature` e `ppOutSignature` descrivono in e out parametri, rispettivamente, come proprietà in un `IWbemClassObject` istanza della classe di sistema [parametry](/windows/desktop/WmiSdk/--parameters).</span><span class="sxs-lookup"><span data-stu-id="a47b6-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="a47b6-132">Le proprietà nella `ppInSignature` sono denominati `Param` *n*, dove *n* è la posizione del parametro nella firma del metodo (ad esempio `Param1`, `Param2`e così via.).</span><span class="sxs-lookup"><span data-stu-id="a47b6-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="a47b6-133">Le proprietà nella `ppOutSignature` sono denominate anche `Param` *n*, e il valore restituito è denominato `ReturnValue`.</span><span class="sxs-lookup"><span data-stu-id="a47b6-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="a47b6-134">Per altre informazioni e un esempio, vedere [IWbemClassObject::GetMethod metodo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span><span class="sxs-lookup"><span data-stu-id="a47b6-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="a47b6-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a47b6-135">Requirements</span></span>

<span data-ttu-id="a47b6-136">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a47b6-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a47b6-137">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a47b6-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="a47b6-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a47b6-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a47b6-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a47b6-139">See also</span></span>

- [<span data-ttu-id="a47b6-140">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="a47b6-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
