---
title: Funzione Clone (riferimenti alle API non gestite)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5957f591dca7df30178660eb3fb074567c285715
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798715"
---
# <a name="clone-function"></a><span data-ttu-id="f1c93-103">Funzione Clone</span><span class="sxs-lookup"><span data-stu-id="f1c93-103">Clone function</span></span>
<span data-ttu-id="f1c93-104">Restituisce un nuovo oggetto che è un clone completo dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f1c93-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f1c93-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1c93-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="f1c93-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1c93-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f1c93-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="f1c93-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f1c93-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="f1c93-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="f1c93-109">out Nuovo oggetto che è un solo completo di `ptr`.</span><span class="sxs-lookup"><span data-stu-id="f1c93-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="f1c93-110">Questo argomento non può `null` essere se riceve la copia dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f1c93-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="f1c93-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f1c93-111">Return value</span></span>

<span data-ttu-id="f1c93-112">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="f1c93-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f1c93-113">Costante</span><span class="sxs-lookup"><span data-stu-id="f1c93-113">Constant</span></span>  |<span data-ttu-id="f1c93-114">Valore</span><span class="sxs-lookup"><span data-stu-id="f1c93-114">Value</span></span>  |<span data-ttu-id="f1c93-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f1c93-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="f1c93-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f1c93-116">0x80041001</span></span> | <span data-ttu-id="f1c93-117">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="f1c93-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f1c93-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f1c93-118">0x80041008</span></span> | <span data-ttu-id="f1c93-119">`null`è stato specificato come parametro e non è valido in questo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f1c93-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f1c93-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f1c93-120">0x80041006</span></span> | <span data-ttu-id="f1c93-121">Memoria insufficiente per clonare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f1c93-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f1c93-122">0</span><span class="sxs-lookup"><span data-stu-id="f1c93-122">0</span></span> | <span data-ttu-id="f1c93-123">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="f1c93-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f1c93-124">Note</span><span class="sxs-lookup"><span data-stu-id="f1c93-124">Remarks</span></span>

<span data-ttu-id="f1c93-125">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="f1c93-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="f1c93-126">L'oggetto clonato è un oggetto COM con conteggio dei riferimenti pari a 1.</span><span class="sxs-lookup"><span data-stu-id="f1c93-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1c93-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1c93-127">Requirements</span></span>  
 <span data-ttu-id="f1c93-128">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1c93-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1c93-129">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f1c93-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f1c93-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c93-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c93-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1c93-131">See also</span></span>

- [<span data-ttu-id="f1c93-132">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="f1c93-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
