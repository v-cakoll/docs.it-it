---
title: Funzione GetMethod (riferimenti alle API non gestite)
description: La funzione GetMethod recupera le informazioni su un metodo.
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
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102581"
---
# <a name="getmethod-function"></a><span data-ttu-id="04f38-103">Funzione GetMethod</span><span class="sxs-lookup"><span data-stu-id="04f38-103">GetMethod function</span></span>

<span data-ttu-id="04f38-104">Recupera le informazioni relative al metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="04f38-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="04f38-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04f38-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="04f38-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="04f38-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="04f38-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="04f38-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="04f38-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="04f38-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="04f38-109">in Nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="04f38-109">[in] The method name.</span></span> <span data-ttu-id="04f38-110">Questo parametro non può essere `null` e deve puntare a una `LPCWSTR`valida.</span><span class="sxs-lookup"><span data-stu-id="04f38-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="04f38-111">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="04f38-111">[in] Reserved.</span></span> <span data-ttu-id="04f38-112">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="04f38-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="04f38-113">out Puntatore all'indirizzo di un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che descrive i parametri in per il metodo.</span><span class="sxs-lookup"><span data-stu-id="04f38-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="04f38-114">Questo parametro viene ignorato se è impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="04f38-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="04f38-115">out Puntatore all'indirizzo di un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che descrive i parametri out al metodo.</span><span class="sxs-lookup"><span data-stu-id="04f38-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="04f38-116">Questo parametro viene ignorato se è impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="04f38-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="04f38-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="04f38-117">Return value</span></span>

<span data-ttu-id="04f38-118">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="04f38-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="04f38-119">Costante</span><span class="sxs-lookup"><span data-stu-id="04f38-119">Constant</span></span>  |<span data-ttu-id="04f38-120">Value</span><span class="sxs-lookup"><span data-stu-id="04f38-120">Value</span></span>  |<span data-ttu-id="04f38-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04f38-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="04f38-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="04f38-122">0x80041002</span></span> | <span data-ttu-id="04f38-123">Impossibile trovare la proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="04f38-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="04f38-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="04f38-124">0x80041006</span></span> | <span data-ttu-id="04f38-125">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="04f38-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="04f38-126">0</span><span class="sxs-lookup"><span data-stu-id="04f38-126">0</span></span> | <span data-ttu-id="04f38-127">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="04f38-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="04f38-128">Note</span><span class="sxs-lookup"><span data-stu-id="04f38-128">Remarks</span></span>

<span data-ttu-id="04f38-129">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .</span><span class="sxs-lookup"><span data-stu-id="04f38-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="04f38-130">Gestione Windows può impostare il puntatore [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) su `null` se il metodo non dispone di parametri in.</span><span class="sxs-lookup"><span data-stu-id="04f38-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="04f38-131">In `ppInSignature` e `ppOutSignature` descrivono rispettivamente i parametri in e out come proprietà in un'istanza `IWbemClassObject` della classe di sistema [_Parameters](/windows/desktop/WmiSdk/--parameters).</span><span class="sxs-lookup"><span data-stu-id="04f38-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="04f38-132">Le proprietà in `ppInSignature` sono denominate `Param`*n*, dove *n* è la posizione del parametro nella firma del metodo, ad esempio `Param1`, `Param2`e così via.</span><span class="sxs-lookup"><span data-stu-id="04f38-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="04f38-133">Anche le proprietà in `ppOutSignature` sono denominate `Param`*n*e il valore restituito è denominato `ReturnValue`.</span><span class="sxs-lookup"><span data-stu-id="04f38-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="04f38-134">Per ulteriori informazioni e un esempio, vedere [Metodo IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span><span class="sxs-lookup"><span data-stu-id="04f38-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="04f38-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04f38-135">Requirements</span></span>

<span data-ttu-id="04f38-136">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04f38-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="04f38-137">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="04f38-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="04f38-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04f38-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="04f38-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04f38-139">See also</span></span>

- [<span data-ttu-id="04f38-140">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="04f38-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
