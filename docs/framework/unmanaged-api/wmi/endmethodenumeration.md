---
title: Funzione EndMethodEnumeration (riferimenti alle API non gestite)
description: La funzione EndMethodEnumeration termina una sequenza di enumerazione dei metodi.
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
ms.openlocfilehash: cdcf49bd748a423b1cebfba88644aa961f1c7b65
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799348"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="d8d52-103">Funzione EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="d8d52-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="d8d52-104">Termina una sequenza di enumerazione avviata con una chiamata alla [funzione BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="d8d52-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d8d52-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8d52-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="d8d52-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8d52-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d8d52-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="d8d52-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d8d52-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="d8d52-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="d8d52-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d8d52-109">Return value</span></span>

<span data-ttu-id="d8d52-110">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="d8d52-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d8d52-111">Costante</span><span class="sxs-lookup"><span data-stu-id="d8d52-111">Constant</span></span>  |<span data-ttu-id="d8d52-112">Valore</span><span class="sxs-lookup"><span data-stu-id="d8d52-112">Value</span></span>  |<span data-ttu-id="d8d52-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8d52-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="d8d52-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="d8d52-114">0x8004101d</span></span> | <span data-ttu-id="d8d52-115">Si è verificato un errore interno.</span><span class="sxs-lookup"><span data-stu-id="d8d52-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d8d52-116">0</span><span class="sxs-lookup"><span data-stu-id="d8d52-116">0</span></span> | <span data-ttu-id="d8d52-117">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="d8d52-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d8d52-118">Note</span><span class="sxs-lookup"><span data-stu-id="d8d52-118">Remarks</span></span>

<span data-ttu-id="d8d52-119">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) .</span><span class="sxs-lookup"><span data-stu-id="d8d52-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="d8d52-120">Il chiamante avvia la sequenza di enumerazione usando la [funzione BeginMethodEnumeration](beginmethodenumeration.md)e quindi chiama la [funzione NextMethod](nextmethod.md )finché il metodo `WBEM_S_NO_MORE_DATA`non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="d8d52-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="d8d52-121">Il chiamante facoltativamente completa la sequenza chiamando `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="d8d52-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="d8d52-122">Il chiamante può terminare l'enumerazione prima chiamando `EndMethodEnumeration` in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="d8d52-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8d52-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8d52-123">Requirements</span></span>  
 <span data-ttu-id="d8d52-124">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8d52-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d52-125">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="d8d52-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d8d52-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d52-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d52-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8d52-127">See also</span></span>

- [<span data-ttu-id="d8d52-128">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="d8d52-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
