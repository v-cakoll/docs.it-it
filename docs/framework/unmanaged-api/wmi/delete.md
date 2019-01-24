---
title: Eliminare la funzione (riferimenti alle API non gestite)
description: La funzione di eliminazione Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0590c639e7cc6622c2283bfa609ccb31d7ce7e2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720574"
---
# <a name="delete-function"></a><span data-ttu-id="3d223-103">Elimina funzione</span><span class="sxs-lookup"><span data-stu-id="3d223-103">Delete function</span></span>
<span data-ttu-id="3d223-104">Elimina la proprietà specificata e tutti i relativi i qualificatori da una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="3d223-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="3d223-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d223-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="3d223-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d223-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3d223-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="3d223-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3d223-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="3d223-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="3d223-109">[in] Il nome della proprietà da eliminare.</span><span class="sxs-lookup"><span data-stu-id="3d223-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="3d223-110">`wszName` deve essere un puntatore a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="3d223-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3d223-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3d223-111">Return value</span></span>

<span data-ttu-id="3d223-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="3d223-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3d223-113">Costante</span><span class="sxs-lookup"><span data-stu-id="3d223-113">Constant</span></span>  |<span data-ttu-id="3d223-114">Valore</span><span class="sxs-lookup"><span data-stu-id="3d223-114">Value</span></span>  |<span data-ttu-id="3d223-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d223-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="3d223-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3d223-116">0x80041001</span></span> | <span data-ttu-id="3d223-117">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="3d223-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="3d223-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="3d223-118">0x80041016</span></span> | <span data-ttu-id="3d223-119">La proprietà non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="3d223-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3d223-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3d223-120">0x80041008</span></span> | <span data-ttu-id="3d223-121">`wszzName` non è valido.</span><span class="sxs-lookup"><span data-stu-id="3d223-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="3d223-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3d223-122">0x80041002</span></span> | <span data-ttu-id="3d223-123">La proprietà specificata non esiste.</span><span class="sxs-lookup"><span data-stu-id="3d223-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3d223-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3d223-124">0x80041006</span></span> | <span data-ttu-id="3d223-125">Non è disponibile memoria sufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="3d223-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="3d223-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="3d223-126">0x8004101c</span></span> | <span data-ttu-id="3d223-127">La proprietà viene ereditata da una classe base.</span><span class="sxs-lookup"><span data-stu-id="3d223-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="3d223-128">La proprietà è una proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="3d223-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3d223-129">0</span><span class="sxs-lookup"><span data-stu-id="3d223-129">0</span></span> | <span data-ttu-id="3d223-130">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3d223-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="3d223-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="3d223-131">0x80041030</span></span> | <span data-ttu-id="3d223-132">La funzione eliminato un valore sostitutivo predefinito per la classe corrente.</span><span class="sxs-lookup"><span data-stu-id="3d223-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="3d223-133">Il valore predefinito per questa proprietà nella classe padre è stata reactiviated.</span><span class="sxs-lookup"><span data-stu-id="3d223-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="3d223-134">Note</span><span class="sxs-lookup"><span data-stu-id="3d223-134">Remarks</span></span>

<span data-ttu-id="3d223-135">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3d223-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3d223-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d223-136">Requirements</span></span>  
 <span data-ttu-id="3d223-137">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d223-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d223-138">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3d223-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3d223-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3d223-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d223-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d223-140">See also</span></span>
- [<span data-ttu-id="3d223-141">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="3d223-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
