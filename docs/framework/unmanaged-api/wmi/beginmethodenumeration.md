---
title: Funzione BeginMethodEnumeration (riferimenti alle API non gestite)
description: La funzione BeginMethodEnumeration avvia un'enumerazione dei metodi dell'oggetto
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d6de2a5ff4d2743c7aca2e46b3af848138c15fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158782"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="9021d-103">Funzione BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="9021d-103">BeginEnumeration function</span></span>
<span data-ttu-id="9021d-104">Avvia un'enumerazione dei metodi disponibili per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9021d-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="9021d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9021d-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="9021d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9021d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9021d-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="9021d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9021d-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="9021d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="9021d-109">[in] Zero (0) per tutti i metodi, o un flag che specifica l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9021d-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="9021d-110">I flag seguenti sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="9021d-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="9021d-111">Costante</span><span class="sxs-lookup"><span data-stu-id="9021d-111">Constant</span></span>  |<span data-ttu-id="9021d-112">Value</span><span class="sxs-lookup"><span data-stu-id="9021d-112">Value</span></span>  |<span data-ttu-id="9021d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9021d-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="9021d-114">0x10</span><span class="sxs-lookup"><span data-stu-id="9021d-114">0x10</span></span> | <span data-ttu-id="9021d-115">Limitare l'enumerazione per i metodi definiti nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="9021d-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="9021d-116">0x20</span><span class="sxs-lookup"><span data-stu-id="9021d-116">0x20</span></span> | <span data-ttu-id="9021d-117">Limitare l'enumerazione delle proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="9021d-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="9021d-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9021d-118">Return value</span></span>

<span data-ttu-id="9021d-119">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="9021d-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9021d-120">Costante</span><span class="sxs-lookup"><span data-stu-id="9021d-120">Constant</span></span>  |<span data-ttu-id="9021d-121">Value</span><span class="sxs-lookup"><span data-stu-id="9021d-121">Value</span></span>  |<span data-ttu-id="9021d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9021d-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9021d-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9021d-123">0x80041008</span></span> | `lEnnumFlags` <span data-ttu-id="9021d-124">è diverso da zero e non è uno dei flag specificati.</span><span class="sxs-lookup"><span data-stu-id="9021d-124">is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9021d-125">0</span><span class="sxs-lookup"><span data-stu-id="9021d-125">0</span></span> | <span data-ttu-id="9021d-126">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9021d-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9021d-127">Note</span><span class="sxs-lookup"><span data-stu-id="9021d-127">Remarks</span></span>

<span data-ttu-id="9021d-128">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) (metodo).</span><span class="sxs-lookup"><span data-stu-id="9021d-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="9021d-129">Questa chiamata al metodo è supportata solo se l'oggetto corrente è una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="9021d-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="9021d-130">Manipolazione di metodo non è disponibile dal [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatori che puntano a istanze.</span><span class="sxs-lookup"><span data-stu-id="9021d-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="9021d-131">L'ordine in cui vengono enumerati i metodi è garantito a essere invariante per una determinata istanza del [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="9021d-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="9021d-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9021d-132">Requirements</span></span>  
 <span data-ttu-id="9021d-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9021d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9021d-134">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9021d-134">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="9021d-135">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9021d-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9021d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9021d-136">See also</span></span>

- [<span data-ttu-id="9021d-137">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="9021d-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
