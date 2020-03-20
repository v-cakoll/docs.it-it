---
title: Clone function (Unmanaged API Reference)
description: La funzione Clone restituisce un nuovo oggetto che è un clone completo di quello corrente.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176851"
---
# <a name="clone-function"></a><span data-ttu-id="039e6-103">Funzione Clone</span><span class="sxs-lookup"><span data-stu-id="039e6-103">Clone function</span></span>
<span data-ttu-id="039e6-104">Restituisce un nuovo oggetto che è un clone completo dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="039e6-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="039e6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="039e6-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="039e6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="039e6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="039e6-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="039e6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="039e6-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="039e6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="039e6-109">[fuori] Un nuovo oggetto che è `ptr`un completo solitario di .</span><span class="sxs-lookup"><span data-stu-id="039e6-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="039e6-110">Questo argomento `null` non può essere se riceve la copia dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="039e6-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="039e6-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="039e6-111">Return value</span></span>

<span data-ttu-id="039e6-112">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="039e6-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="039e6-113">Costante</span><span class="sxs-lookup"><span data-stu-id="039e6-113">Constant</span></span>  |<span data-ttu-id="039e6-114">valore</span><span class="sxs-lookup"><span data-stu-id="039e6-114">Value</span></span>  |<span data-ttu-id="039e6-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="039e6-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="039e6-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="039e6-116">0x80041001</span></span> | <span data-ttu-id="039e6-117">C'è stato un fallimento generale.</span><span class="sxs-lookup"><span data-stu-id="039e6-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="039e6-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="039e6-118">0x80041008</span></span> | <span data-ttu-id="039e6-119">`null`è stato specificato come parametro e non è legale in questo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="039e6-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="039e6-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="039e6-120">0x80041006</span></span> | <span data-ttu-id="039e6-121">Non è disponibile memoria sufficiente per clonare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="039e6-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="039e6-122">0</span><span class="sxs-lookup"><span data-stu-id="039e6-122">0</span></span> | <span data-ttu-id="039e6-123">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="039e6-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="039e6-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="039e6-124">Remarks</span></span>

<span data-ttu-id="039e6-125">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::Clone.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)</span><span class="sxs-lookup"><span data-stu-id="039e6-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="039e6-126">L'oggetto clonato è un oggetto COM con un conteggio dei riferimenti pari a 1.The cloned object is a COM object that has a reference count of 1.</span><span class="sxs-lookup"><span data-stu-id="039e6-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="039e6-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="039e6-127">Requirements</span></span>  
 <span data-ttu-id="039e6-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="039e6-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="039e6-129">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="039e6-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="039e6-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="039e6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="039e6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="039e6-131">See also</span></span>

- [<span data-ttu-id="039e6-132">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="039e6-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
