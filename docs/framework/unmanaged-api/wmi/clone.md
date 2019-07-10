---
title: 'IMetaDataImport:: Clone (funzione) (riferimenti alle API non gestite)'
description: La funzione Clone restituisce un nuovo oggetto che costituisce un clone completo dell'oggetto corrente.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80faf1a5a6297f5b105fdb609366f6774f8692b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761645"
---
# <a name="clone-function"></a><span data-ttu-id="26a78-103">Funzione Clone</span><span class="sxs-lookup"><span data-stu-id="26a78-103">Clone function</span></span>
<span data-ttu-id="26a78-104">Restituisce un nuovo oggetto che è un clone completo dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="26a78-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="26a78-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26a78-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="26a78-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="26a78-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="26a78-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="26a78-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="26a78-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="26a78-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="26a78-109">[out] Un nuovo oggetto che è stato completato un unico di `ptr`.</span><span class="sxs-lookup"><span data-stu-id="26a78-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="26a78-110">Questo argomento non può essere `null` se riceve la copia dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="26a78-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="26a78-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="26a78-111">Return value</span></span>

<span data-ttu-id="26a78-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="26a78-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="26a78-113">Costante</span><span class="sxs-lookup"><span data-stu-id="26a78-113">Constant</span></span>  |<span data-ttu-id="26a78-114">Value</span><span class="sxs-lookup"><span data-stu-id="26a78-114">Value</span></span>  |<span data-ttu-id="26a78-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26a78-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="26a78-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="26a78-116">0x80041001</span></span> | <span data-ttu-id="26a78-117">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="26a78-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="26a78-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="26a78-118">0x80041008</span></span> | <span data-ttu-id="26a78-119">`null` è stato specificato come parametro, e non è consentito in questo tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="26a78-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="26a78-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="26a78-120">0x80041006</span></span> | <span data-ttu-id="26a78-121">Memoria insufficiente è disponibile per clonare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="26a78-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="26a78-122">0</span><span class="sxs-lookup"><span data-stu-id="26a78-122">0</span></span> | <span data-ttu-id="26a78-123">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="26a78-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="26a78-124">Note</span><span class="sxs-lookup"><span data-stu-id="26a78-124">Remarks</span></span>

<span data-ttu-id="26a78-125">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) (metodo).</span><span class="sxs-lookup"><span data-stu-id="26a78-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="26a78-126">Oggetto clonato è un oggetto COM che dispone di un conteggio dei riferimenti pari a 1.</span><span class="sxs-lookup"><span data-stu-id="26a78-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="26a78-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26a78-127">Requirements</span></span>  
 <span data-ttu-id="26a78-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a78-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a78-129">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="26a78-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="26a78-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="26a78-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a78-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26a78-131">See also</span></span>

- [<span data-ttu-id="26a78-132">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="26a78-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
