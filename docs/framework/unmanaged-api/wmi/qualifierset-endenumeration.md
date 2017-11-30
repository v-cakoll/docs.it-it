---
title: Funzione QualifierSet_EndEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_EndEnumeration termina un'enumerazione.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="5cd69-103">QualifierSet_EndEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="5cd69-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="5cd69-104">Termina l'enumerazione iniziato con una chiamata al [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="5cd69-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5cd69-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cd69-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="5cd69-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5cd69-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5cd69-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="5cd69-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="5cd69-108">[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="5cd69-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="5cd69-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5cd69-109">Return value</span></span>

<span data-ttu-id="5cd69-110">Il seguente valore restituito da questa funzione è definito nel *WbemCli.h* file di intestazione, oppure definire come costante nel codice:</span><span class="sxs-lookup"><span data-stu-id="5cd69-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="5cd69-111">Costante</span><span class="sxs-lookup"><span data-stu-id="5cd69-111">Constant</span></span>  |<span data-ttu-id="5cd69-112">Valore</span><span class="sxs-lookup"><span data-stu-id="5cd69-112">Value</span></span>  |<span data-ttu-id="5cd69-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5cd69-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5cd69-114">0</span><span class="sxs-lookup"><span data-stu-id="5cd69-114">0</span></span> | <span data-ttu-id="5cd69-115">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="5cd69-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5cd69-116">Note</span><span class="sxs-lookup"><span data-stu-id="5cd69-116">Remarks</span></span>

<span data-ttu-id="5cd69-117">Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="5cd69-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="5cd69-118">Questa chiamata è consigliata, ma non necessario.</span><span class="sxs-lookup"><span data-stu-id="5cd69-118">This call is recommended, but not required.</span></span> <span data-ttu-id="5cd69-119">Rilascia immediatamente le risorse associate all'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5cd69-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="5cd69-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cd69-120">Requirements</span></span>  

<span data-ttu-id="5cd69-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cd69-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="5cd69-122">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5cd69-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="5cd69-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5cd69-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd69-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cd69-124">See also</span></span>  
[<span data-ttu-id="5cd69-125">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="5cd69-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
