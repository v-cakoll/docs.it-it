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
ms.openlocfilehash: bf9cca10a580af7991889de6993e931347fc27ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120958"
---
# <a name="clone-function"></a><span data-ttu-id="0db19-103">Funzione Clone</span><span class="sxs-lookup"><span data-stu-id="0db19-103">Clone function</span></span>
<span data-ttu-id="0db19-104">Restituisce un nuovo oggetto che è un clone completo dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="0db19-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0db19-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0db19-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="0db19-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0db19-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0db19-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="0db19-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0db19-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="0db19-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="0db19-109">[out] Un nuovo oggetto che è stato completato un unico di `ptr`.</span><span class="sxs-lookup"><span data-stu-id="0db19-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="0db19-110">Questo argomento non può essere `null` se riceve la copia dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="0db19-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="0db19-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0db19-111">Return value</span></span>

<span data-ttu-id="0db19-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="0db19-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0db19-113">Costante</span><span class="sxs-lookup"><span data-stu-id="0db19-113">Constant</span></span>  |<span data-ttu-id="0db19-114">Value</span><span class="sxs-lookup"><span data-stu-id="0db19-114">Value</span></span>  |<span data-ttu-id="0db19-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0db19-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="0db19-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0db19-116">0x80041001</span></span> | <span data-ttu-id="0db19-117">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="0db19-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0db19-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0db19-118">0x80041008</span></span> | `null` <span data-ttu-id="0db19-119">è stato specificato come parametro, e non è consentito in questo tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0db19-119">was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0db19-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0db19-120">0x80041006</span></span> | <span data-ttu-id="0db19-121">Memoria insufficiente è disponibile per clonare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0db19-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0db19-122">0</span><span class="sxs-lookup"><span data-stu-id="0db19-122">0</span></span> | <span data-ttu-id="0db19-123">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0db19-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0db19-124">Note</span><span class="sxs-lookup"><span data-stu-id="0db19-124">Remarks</span></span>

<span data-ttu-id="0db19-125">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) (metodo).</span><span class="sxs-lookup"><span data-stu-id="0db19-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="0db19-126">Oggetto clonato è un oggetto COM che dispone di un conteggio dei riferimenti pari a 1.</span><span class="sxs-lookup"><span data-stu-id="0db19-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="0db19-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0db19-127">Requirements</span></span>  
 <span data-ttu-id="0db19-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0db19-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0db19-129">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0db19-129">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="0db19-130">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0db19-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0db19-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0db19-131">See also</span></span>

- [<span data-ttu-id="0db19-132">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="0db19-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
