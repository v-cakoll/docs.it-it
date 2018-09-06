---
title: Funzione QualifierSet_Delete (riferimenti alle API non gestite)
description: La funzione QualifierSet_Delete consente di eliminare un qualificatore in base al nome.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ca4cc9fb65d1a4bd8713f969bbda5551ce5a2e2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881798"
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="d315e-103">QualifierSet_Delete (funzione)</span><span class="sxs-lookup"><span data-stu-id="d315e-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="d315e-104">Elimina un qualificatore specificato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="d315e-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d315e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d315e-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="d315e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d315e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d315e-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="d315e-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="d315e-108">[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.</span><span class="sxs-lookup"><span data-stu-id="d315e-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="d315e-109">[in] Il nome del qualificatore da eliminare.</span><span class="sxs-lookup"><span data-stu-id="d315e-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="d315e-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d315e-110">Return value</span></span>

<span data-ttu-id="d315e-111">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="d315e-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d315e-112">Costante</span><span class="sxs-lookup"><span data-stu-id="d315e-112">Constant</span></span>  |<span data-ttu-id="d315e-113">Valore</span><span class="sxs-lookup"><span data-stu-id="d315e-113">Value</span></span>  |<span data-ttu-id="d315e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d315e-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d315e-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d315e-115">0x80041008</span></span> | <span data-ttu-id="d315e-116">Il `wszName` parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="d315e-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="d315e-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="d315e-117">0x80041016</span></span> | <span data-ttu-id="d315e-118">L'eliminazione di questo qualificatore non è valido.</span><span class="sxs-lookup"><span data-stu-id="d315e-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="d315e-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="d315e-119">0x80041002</span></span> | <span data-ttu-id="d315e-120">Il qualificatore specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="d315e-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d315e-121">0</span><span class="sxs-lookup"><span data-stu-id="d315e-121">0</span></span> | <span data-ttu-id="d315e-122">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d315e-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="d315e-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="d315e-123">0x40002</span></span> | <span data-ttu-id="d315e-124">La sostituzione locale è stata eliminata e il qualificatore originale dall'oggetto padre ha ripreso l'ambito.</span><span class="sxs-lookup"><span data-stu-id="d315e-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d315e-125">Note</span><span class="sxs-lookup"><span data-stu-id="d315e-125">Remarks</span></span>

<span data-ttu-id="d315e-126">Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d315e-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="d315e-127">A causa di regole di propagazione di qualificatore, un qualificatore particolare potrebbe sono stato ereditato da un altro oggetto e semplicemente sottoposto a override nella classe corrente o istanza.</span><span class="sxs-lookup"><span data-stu-id="d315e-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="d315e-128">In questo caso, il `QualifierSet_Delete` metodo reimposta il qualificatore per il valore originale ereditato.</span><span class="sxs-lookup"><span data-stu-id="d315e-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="d315e-129">In questo caso, la funzione restituisce il codice di stato `WBEM_S_RESET_TO_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="d315e-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="d315e-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d315e-130">Requirements</span></span>  
 <span data-ttu-id="d315e-131">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d315e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d315e-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d315e-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d315e-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d315e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d315e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d315e-134">See also</span></span>  
[<span data-ttu-id="d315e-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="d315e-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
