---
title: Funzione EndEnumeration (riferimenti alle API non gestite)
description: La funzione EndEnumeration termina un'enumerazione.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: EndEnumeration
helpviewer_keywords: EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 043fce26870e5af2850b9f2e91e7e97c7bee6c90
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="endenumeration-function"></a><span data-ttu-id="ff507-103">EndEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="ff507-103">EndEnumeration function</span></span>
<span data-ttu-id="ff507-104">Termina una sequenza di enumerazione avviata con una chiamata al [BeginEnumeration funzione](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ff507-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ff507-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff507-105">Syntax</span></span>  
  
```  
HRESULT EndEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="ff507-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff507-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ff507-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ff507-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ff507-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="ff507-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>


## <a name="return-value"></a><span data-ttu-id="ff507-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ff507-109">Return value</span></span>

<span data-ttu-id="ff507-110">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ff507-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ff507-111">Costante</span><span class="sxs-lookup"><span data-stu-id="ff507-111">Constant</span></span>  |<span data-ttu-id="ff507-112">Valore</span><span class="sxs-lookup"><span data-stu-id="ff507-112">Value</span></span>  |<span data-ttu-id="ff507-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff507-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="ff507-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ff507-114">0x80041001</span></span> | <span data-ttu-id="ff507-115">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="ff507-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ff507-116">0</span><span class="sxs-lookup"><span data-stu-id="ff507-116">0</span></span> | <span data-ttu-id="ff507-117">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ff507-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ff507-118">Note</span><span class="sxs-lookup"><span data-stu-id="ff507-118">Remarks</span></span>

<span data-ttu-id="ff507-119">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::EndEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="ff507-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="ff507-120">Una chiamata al `EndEnumeration` funzione non è obbligatorio, ma è consigliabile perché rilascia le risorse associate all'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ff507-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="ff507-121">Tuttavia, il resoruces vengono deallocate automaticamente quando viene avviata l'enumerazione successiva o l'oggetto viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="ff507-121">However, the resoruces are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff507-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff507-122">Requirements</span></span>  
 <span data-ttu-id="ff507-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff507-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff507-124">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ff507-124">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ff507-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ff507-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff507-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff507-126">See also</span></span>  
[<span data-ttu-id="ff507-127">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ff507-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
