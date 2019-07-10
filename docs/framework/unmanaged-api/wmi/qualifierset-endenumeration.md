---
title: Funzione QualifierSet_EndEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_EndEnumeration termina un'enumerazione.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 206d6448835b60c55b378636ff5daa5fa4f8b5d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782589"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="12418-103">QualifierSet_EndEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="12418-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="12418-104">Termina l'enumerazione iniziato con una chiamata per il [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="12418-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="12418-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12418-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="12418-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="12418-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="12418-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="12418-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="12418-108">[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.</span><span class="sxs-lookup"><span data-stu-id="12418-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="12418-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="12418-109">Return value</span></span>

<span data-ttu-id="12418-110">Il valore seguente restituito da questa funzione è definito nel *WbemCli.h* file di intestazione, oppure è possibile definirlo come costante nel codice:</span><span class="sxs-lookup"><span data-stu-id="12418-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="12418-111">Costante</span><span class="sxs-lookup"><span data-stu-id="12418-111">Constant</span></span>  |<span data-ttu-id="12418-112">Value</span><span class="sxs-lookup"><span data-stu-id="12418-112">Value</span></span>  |<span data-ttu-id="12418-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12418-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="12418-114">0</span><span class="sxs-lookup"><span data-stu-id="12418-114">0</span></span> | <span data-ttu-id="12418-115">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="12418-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="12418-116">Note</span><span class="sxs-lookup"><span data-stu-id="12418-116">Remarks</span></span>

<span data-ttu-id="12418-117">Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) (metodo).</span><span class="sxs-lookup"><span data-stu-id="12418-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="12418-118">Questa chiamata è consigliata, ma non obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="12418-118">This call is recommended, but not required.</span></span> <span data-ttu-id="12418-119">Rilascia immediatamente le risorse associate all'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="12418-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="12418-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12418-120">Requirements</span></span>  

<span data-ttu-id="12418-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12418-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="12418-122">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="12418-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="12418-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="12418-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12418-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12418-124">See also</span></span>

- [<span data-ttu-id="12418-125">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="12418-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
