---
title: Funzione BeginMethodEnumeration (riferimenti alle API non gestite)
description: La funzione BeginMethodEnumeration avvia un'enumerazione dei metodi dell'oggetto
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginMethodEnumeration
helpviewer_keywords: BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d843c40a8ab0dd1c48a08126b8c7472505a1732
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="ca643-103">BeginEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="ca643-103">BeginEnumeration function</span></span>
<span data-ttu-id="ca643-104">Avvia un'enumerazione dei metodi disponibili per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ca643-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ca643-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca643-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="ca643-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca643-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ca643-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ca643-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ca643-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="ca643-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="ca643-109">[in] Zero (0) per tutti i metodi o di un flag che specifica l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ca643-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="ca643-110">I flag seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ca643-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="ca643-111">Costante</span><span class="sxs-lookup"><span data-stu-id="ca643-111">Constant</span></span>  |<span data-ttu-id="ca643-112">Valore</span><span class="sxs-lookup"><span data-stu-id="ca643-112">Value</span></span>  |<span data-ttu-id="ca643-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca643-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="ca643-114">0x10</span><span class="sxs-lookup"><span data-stu-id="ca643-114">0x10</span></span> | <span data-ttu-id="ca643-115">Limitare l'enumerazione per i metodi definiti nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="ca643-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="ca643-116">0x20</span><span class="sxs-lookup"><span data-stu-id="ca643-116">0x20</span></span> | <span data-ttu-id="ca643-117">Limitare l'enumerazione di proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="ca643-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="ca643-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ca643-118">Return value</span></span>

<span data-ttu-id="ca643-119">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ca643-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ca643-120">Costante</span><span class="sxs-lookup"><span data-stu-id="ca643-120">Constant</span></span>  |<span data-ttu-id="ca643-121">Valore</span><span class="sxs-lookup"><span data-stu-id="ca643-121">Value</span></span>  |<span data-ttu-id="ca643-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca643-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ca643-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ca643-123">0x80041008</span></span> | <span data-ttu-id="ca643-124">`lEnnumFlags`è diverso da zero e non è uno dei flag specificati.</span><span class="sxs-lookup"><span data-stu-id="ca643-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ca643-125">0</span><span class="sxs-lookup"><span data-stu-id="ca643-125">0</span></span> | <span data-ttu-id="ca643-126">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ca643-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ca643-127">Note</span><span class="sxs-lookup"><span data-stu-id="ca643-127">Remarks</span></span>

<span data-ttu-id="ca643-128">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="ca643-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="ca643-129">Questa chiamata al metodo è supportata solo se l'oggetto corrente è una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="ca643-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="ca643-130">Manipolazione di metodo non è disponibile da [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) puntatori che puntano alle istanze.</span><span class="sxs-lookup"><span data-stu-id="ca643-130">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to instances.</span></span> <span data-ttu-id="ca643-131">L'ordine in cui vengono enumerati i metodi è sicuramente invariante per una determinata istanza di [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca643-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="ca643-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca643-132">Requirements</span></span>  
 <span data-ttu-id="ca643-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca643-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca643-134">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ca643-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ca643-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ca643-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca643-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca643-136">See also</span></span>  
[<span data-ttu-id="ca643-137">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ca643-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
