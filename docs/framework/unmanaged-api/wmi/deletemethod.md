---
title: Funzione DeleteMethod (riferimenti alle API non gestite)
description: La funzione DeleteMethod Elimina il metodo specificato da una definizione di classe CIM.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 291d5d0461da8d130d41f9a0eca67ea3be42b4bc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746818"
---
# <a name="deletemethod-function"></a><span data-ttu-id="b0f08-103">Funzione DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="b0f08-103">DeleteMethod function</span></span>
<span data-ttu-id="b0f08-104">Elimina il metodo specificato da una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="b0f08-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b0f08-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0f08-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="b0f08-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0f08-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b0f08-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="b0f08-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b0f08-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="b0f08-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="b0f08-109">[in] Il nome del metodo da rimuovere dalla tabella della classe.</span><span class="sxs-lookup"><span data-stu-id="b0f08-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="b0f08-110">`wszName` deve essere un puntatore a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="b0f08-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b0f08-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b0f08-111">Return value</span></span>

<span data-ttu-id="b0f08-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="b0f08-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b0f08-113">Costante</span><span class="sxs-lookup"><span data-stu-id="b0f08-113">Constant</span></span>  |<span data-ttu-id="b0f08-114">Value</span><span class="sxs-lookup"><span data-stu-id="b0f08-114">Value</span></span>  |<span data-ttu-id="b0f08-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0f08-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="b0f08-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b0f08-116">0x80041002</span></span> | <span data-ttu-id="b0f08-117">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="b0f08-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b0f08-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b0f08-118">0x80041006</span></span> | <span data-ttu-id="b0f08-119">Non è disponibile memoria sufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="b0f08-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b0f08-120">0</span><span class="sxs-lookup"><span data-stu-id="b0f08-120">0</span></span> | <span data-ttu-id="b0f08-121">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b0f08-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b0f08-122">Note</span><span class="sxs-lookup"><span data-stu-id="b0f08-122">Remarks</span></span>

<span data-ttu-id="b0f08-123">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b0f08-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="b0f08-124">L'eliminazione di metodo non è supportata per [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatori che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="b0f08-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="b0f08-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0f08-125">Requirements</span></span>  
 <span data-ttu-id="b0f08-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0f08-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0f08-127">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b0f08-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b0f08-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b0f08-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f08-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0f08-129">See also</span></span>

- [<span data-ttu-id="b0f08-130">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b0f08-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
