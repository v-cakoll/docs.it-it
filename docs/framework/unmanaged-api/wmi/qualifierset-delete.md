---
title: QualifierSet_Delete function (Unmanaged API Reference)
description: La funzione QualifierSet_Delete elimina un qualificatore in base al nome.
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
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174901"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="3e38c-103">Funzione QualifierSet_Delete</span><span class="sxs-lookup"><span data-stu-id="3e38c-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="3e38c-104">Elimina un qualificatore specificato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="3e38c-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3e38c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e38c-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="3e38c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3e38c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3e38c-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3e38c-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="3e38c-108">`ptr`[in] Puntatore a [un'istanza di IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="3e38c-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="3e38c-109">`wszName`[in] Nome del qualificatore da eliminare.</span><span class="sxs-lookup"><span data-stu-id="3e38c-109">`wszName` [in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="3e38c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3e38c-110">Return value</span></span>

<span data-ttu-id="3e38c-111">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="3e38c-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3e38c-112">Costante</span><span class="sxs-lookup"><span data-stu-id="3e38c-112">Constant</span></span>  |<span data-ttu-id="3e38c-113">valore</span><span class="sxs-lookup"><span data-stu-id="3e38c-113">Value</span></span>  |<span data-ttu-id="3e38c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e38c-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3e38c-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3e38c-115">0x80041008</span></span> | <span data-ttu-id="3e38c-116">Il parametro `wszName` non è valido.</span><span class="sxs-lookup"><span data-stu-id="3e38c-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="3e38c-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="3e38c-117">0x80041016</span></span> | <span data-ttu-id="3e38c-118">L'eliminazione di questo qualificatore non è valida.</span><span class="sxs-lookup"><span data-stu-id="3e38c-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="3e38c-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3e38c-119">0x80041002</span></span> | <span data-ttu-id="3e38c-120">Il qualificatore specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="3e38c-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3e38c-121">0</span><span class="sxs-lookup"><span data-stu-id="3e38c-121">0</span></span> | <span data-ttu-id="3e38c-122">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3e38c-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="3e38c-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="3e38c-123">0x40002</span></span> | <span data-ttu-id="3e38c-124">L'override locale è stato eliminato e il qualificatore originale dall'oggetto padre ha ripreso l'ambito.</span><span class="sxs-lookup"><span data-stu-id="3e38c-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3e38c-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3e38c-125">Remarks</span></span>

<span data-ttu-id="3e38c-126">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemQualifierSet::Delete.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)</span><span class="sxs-lookup"><span data-stu-id="3e38c-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="3e38c-127">A causa delle regole di propagazione del qualificatore, un qualificatore specifico potrebbe essere stato ereditato da un altro oggetto e semplicemente sottoposto a override nella classe o nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="3e38c-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="3e38c-128">In questo caso, il `QualifierSet_Delete` metodo reimposta il qualificatore sul valore ereditato originale.</span><span class="sxs-lookup"><span data-stu-id="3e38c-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="3e38c-129">La funzione in questo caso `WBEM_S_RESET_TO_DEFAULT`restituisce il codice di stato .</span><span class="sxs-lookup"><span data-stu-id="3e38c-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e38c-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e38c-130">Requirements</span></span>  
 <span data-ttu-id="3e38c-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e38c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e38c-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3e38c-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3e38c-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3e38c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e38c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e38c-134">See also</span></span>

- [<span data-ttu-id="3e38c-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="3e38c-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
