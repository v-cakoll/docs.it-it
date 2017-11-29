---
title: Funzione EndMethodEnumeration (riferimenti alle API non gestite)
description: La funzione EndMethodEnumeration termina una sequenza di enumerazione del metodo.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: EndMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: EndMethodEnumeration
helpviewer_keywords: EndMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1b768292811a752e7a319f853ca8eff85f1bb08
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="ecbbc-103">EndMethodEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="ecbbc-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="ecbbc-104">Termina una sequenza di enumerazione avviata con una chiamata al [BeginMethodEnumeration funzione](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ecbbc-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ecbbc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecbbc-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="ecbbc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ecbbc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ecbbc-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ecbbc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ecbbc-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="ecbbc-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="ecbbc-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ecbbc-109">Return value</span></span>

<span data-ttu-id="ecbbc-110">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ecbbc-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ecbbc-111">Costante</span><span class="sxs-lookup"><span data-stu-id="ecbbc-111">Constant</span></span>  |<span data-ttu-id="ecbbc-112">Valore</span><span class="sxs-lookup"><span data-stu-id="ecbbc-112">Value</span></span>  |<span data-ttu-id="ecbbc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecbbc-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="ecbbc-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="ecbbc-114">0x8004101d</span></span> | <span data-ttu-id="ecbbc-115">Si è verificato un errore interno.</span><span class="sxs-lookup"><span data-stu-id="ecbbc-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ecbbc-116">0</span><span class="sxs-lookup"><span data-stu-id="ecbbc-116">0</span></span> | <span data-ttu-id="ecbbc-117">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ecbbc-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ecbbc-118">Note</span><span class="sxs-lookup"><span data-stu-id="ecbbc-118">Remarks</span></span>

<span data-ttu-id="ecbbc-119">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="ecbbc-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="ecbbc-120">Il chiamante ha inizio la sequenza di enumerazione utilizzando [BeginMethodEnumeration funzione](beginmethodenumeration.md)e quindi chiama il [NextMethod funzione](nextmethod.md )finché il metodo restituisce `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="ecbbc-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="ecbbc-121">Il chiamante termina, facoltativamente, la sequenza chiamando `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="ecbbc-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="ecbbc-122">Il chiamante può terminare in anticipo l'enumerazione chiamando `EndMethodEnumeration` in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ecbbc-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="ecbbc-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ecbbc-123">Requirements</span></span>  
 <span data-ttu-id="ecbbc-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecbbc-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbbc-125">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ecbbc-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ecbbc-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ecbbc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbbc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecbbc-127">See also</span></span>  
[<span data-ttu-id="ecbbc-128">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ecbbc-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
