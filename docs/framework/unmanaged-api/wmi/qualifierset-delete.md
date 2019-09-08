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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bc26a16650a5beecc17898e0421e79536713deb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798331"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="98088-103">QualifierSet_Delete (funzione)</span><span class="sxs-lookup"><span data-stu-id="98088-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="98088-104">Elimina un qualificatore specificato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="98088-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="98088-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98088-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="98088-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="98088-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="98088-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="98088-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="98088-108">in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="98088-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="98088-109">in Nome del qualificatore da eliminare.</span><span class="sxs-lookup"><span data-stu-id="98088-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="98088-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="98088-110">Return value</span></span>

<span data-ttu-id="98088-111">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="98088-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="98088-112">Costante</span><span class="sxs-lookup"><span data-stu-id="98088-112">Constant</span></span>  |<span data-ttu-id="98088-113">Valore</span><span class="sxs-lookup"><span data-stu-id="98088-113">Value</span></span>  |<span data-ttu-id="98088-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="98088-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="98088-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="98088-115">0x80041008</span></span> | <span data-ttu-id="98088-116">Il parametro `wszName` non è valido.</span><span class="sxs-lookup"><span data-stu-id="98088-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="98088-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="98088-117">0x80041016</span></span> | <span data-ttu-id="98088-118">L'eliminazione di questo qualificatore non è valida.</span><span class="sxs-lookup"><span data-stu-id="98088-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="98088-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="98088-119">0x80041002</span></span> | <span data-ttu-id="98088-120">Il qualificatore specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="98088-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="98088-121">0</span><span class="sxs-lookup"><span data-stu-id="98088-121">0</span></span> | <span data-ttu-id="98088-122">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="98088-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="98088-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="98088-123">0x40002</span></span> | <span data-ttu-id="98088-124">L'override locale è stato eliminato e il qualificatore originale dall'oggetto padre ha ripreso l'ambito.</span><span class="sxs-lookup"><span data-stu-id="98088-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="98088-125">Note</span><span class="sxs-lookup"><span data-stu-id="98088-125">Remarks</span></span>

<span data-ttu-id="98088-126">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet::D Elimina](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) .</span><span class="sxs-lookup"><span data-stu-id="98088-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="98088-127">A causa delle regole di propagazione dei qualificatori, è possibile che un qualificatore specifico sia stato ereditato da un altro oggetto e sottoposto a override nella classe o nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="98088-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="98088-128">In questo caso, il `QualifierSet_Delete` metodo reimposta il qualificatore sul valore ereditato originale.</span><span class="sxs-lookup"><span data-stu-id="98088-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="98088-129">La funzione in questo caso restituisce il codice `WBEM_S_RESET_TO_DEFAULT`di stato.</span><span class="sxs-lookup"><span data-stu-id="98088-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="98088-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98088-130">Requirements</span></span>  
 <span data-ttu-id="98088-131">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98088-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98088-132">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="98088-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="98088-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="98088-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98088-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98088-134">See also</span></span>

- [<span data-ttu-id="98088-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="98088-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
