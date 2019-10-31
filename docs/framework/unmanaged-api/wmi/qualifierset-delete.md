---
title: Funzione QualifierSet_Delete (riferimenti alle API non gestite)
description: La funzione QualifierSet_Delete Elimina un qualificatore in base al nome.
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
ms.openlocfilehash: e7bedcb5c56f9976f8dfd2619081971075d0d809
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127304"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="0640d-103">QualifierSet_Delete (funzione)</span><span class="sxs-lookup"><span data-stu-id="0640d-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="0640d-104">Elimina un qualificatore specificato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="0640d-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0640d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0640d-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="0640d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0640d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0640d-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="0640d-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="0640d-108">in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="0640d-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="0640d-109">in Nome del qualificatore da eliminare.</span><span class="sxs-lookup"><span data-stu-id="0640d-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="0640d-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0640d-110">Return value</span></span>

<span data-ttu-id="0640d-111">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="0640d-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0640d-112">Costante</span><span class="sxs-lookup"><span data-stu-id="0640d-112">Constant</span></span>  |<span data-ttu-id="0640d-113">Value</span><span class="sxs-lookup"><span data-stu-id="0640d-113">Value</span></span>  |<span data-ttu-id="0640d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0640d-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0640d-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0640d-115">0x80041008</span></span> | <span data-ttu-id="0640d-116">Il parametro `wszName` non è valido.</span><span class="sxs-lookup"><span data-stu-id="0640d-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="0640d-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="0640d-117">0x80041016</span></span> | <span data-ttu-id="0640d-118">L'eliminazione di questo qualificatore non è valida.</span><span class="sxs-lookup"><span data-stu-id="0640d-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="0640d-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0640d-119">0x80041002</span></span> | <span data-ttu-id="0640d-120">Il qualificatore specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="0640d-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0640d-121">0</span><span class="sxs-lookup"><span data-stu-id="0640d-121">0</span></span> | <span data-ttu-id="0640d-122">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="0640d-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="0640d-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="0640d-123">0x40002</span></span> | <span data-ttu-id="0640d-124">L'override locale è stato eliminato e il qualificatore originale dall'oggetto padre ha ripreso l'ambito.</span><span class="sxs-lookup"><span data-stu-id="0640d-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0640d-125">Note</span><span class="sxs-lookup"><span data-stu-id="0640d-125">Remarks</span></span>

<span data-ttu-id="0640d-126">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet::D Elimina](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) .</span><span class="sxs-lookup"><span data-stu-id="0640d-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="0640d-127">A causa delle regole di propagazione dei qualificatori, è possibile che un qualificatore specifico sia stato ereditato da un altro oggetto e sottoposto a override nella classe o nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="0640d-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="0640d-128">In questo caso, il metodo `QualifierSet_Delete` Reimposta il qualificatore sul valore ereditato originale.</span><span class="sxs-lookup"><span data-stu-id="0640d-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="0640d-129">La funzione in questo caso restituisce il codice di stato `WBEM_S_RESET_TO_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="0640d-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0640d-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0640d-130">Requirements</span></span>  
 <span data-ttu-id="0640d-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0640d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0640d-132">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="0640d-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0640d-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0640d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0640d-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0640d-134">See also</span></span>

- [<span data-ttu-id="0640d-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="0640d-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
