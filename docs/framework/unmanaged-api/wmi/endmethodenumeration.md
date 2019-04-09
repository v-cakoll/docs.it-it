---
title: Funzione EndMethodEnumeration (riferimenti alle API non gestite)
description: La funzione EndMethodEnumeration termina una sequenza di enumerazione (metodo).
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7f29c365e9f6ba85f85ceb232f7af89446af2a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213051"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="99e00-103">Funzione EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="99e00-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="99e00-104">Termina una sequenza di enumerazione avviata con una chiamata per il [BeginMethodEnumeration funzione](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="99e00-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="99e00-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99e00-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="99e00-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="99e00-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="99e00-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="99e00-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="99e00-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="99e00-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="99e00-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="99e00-109">Return value</span></span>

<span data-ttu-id="99e00-110">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="99e00-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="99e00-111">Costante</span><span class="sxs-lookup"><span data-stu-id="99e00-111">Constant</span></span>  |<span data-ttu-id="99e00-112">Value</span><span class="sxs-lookup"><span data-stu-id="99e00-112">Value</span></span>  |<span data-ttu-id="99e00-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99e00-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="99e00-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="99e00-114">0x8004101d</span></span> | <span data-ttu-id="99e00-115">Si è verificato un errore interno.</span><span class="sxs-lookup"><span data-stu-id="99e00-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="99e00-116">0</span><span class="sxs-lookup"><span data-stu-id="99e00-116">0</span></span> | <span data-ttu-id="99e00-117">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="99e00-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="99e00-118">Note</span><span class="sxs-lookup"><span data-stu-id="99e00-118">Remarks</span></span>

<span data-ttu-id="99e00-119">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) (metodo).</span><span class="sxs-lookup"><span data-stu-id="99e00-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="99e00-120">Il chiamante ha inizio la sequenza di enumerazione utilizzando [funzione BeginMethodEnumeration](beginmethodenumeration.md)e quindi chiama il [NextMethod funzione](nextmethod.md )fino a quando il metodo restituisce `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="99e00-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="99e00-121">Il chiamante, facoltativamente, termina la sequenza chiamando `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="99e00-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="99e00-122">Il chiamante può terminare l'enumerazione all'inizio chiamando `EndMethodEnumeration` in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="99e00-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="99e00-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99e00-123">Requirements</span></span>  
 <span data-ttu-id="99e00-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99e00-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99e00-125">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="99e00-125">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="99e00-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="99e00-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99e00-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99e00-127">See also</span></span>

- [<span data-ttu-id="99e00-128">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="99e00-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
