---
title: Funzione EndEnumeration (riferimenti alle API non gestite)
description: La funzione EndEnumeration termina un'enumerazione.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b9fd1f094c8fb56c94421a07437aa25a3549c487
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132049"
---
# <a name="endenumeration-function"></a><span data-ttu-id="08332-103">Funzione EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="08332-103">EndEnumeration function</span></span>

<span data-ttu-id="08332-104">Termina una sequenza di enumerazione avviata con una chiamata alla [funzione BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="08332-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="08332-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08332-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="08332-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="08332-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="08332-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="08332-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="08332-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="08332-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="08332-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08332-109">Return value</span></span>

<span data-ttu-id="08332-110">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="08332-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="08332-111">Costante</span><span class="sxs-lookup"><span data-stu-id="08332-111">Constant</span></span>  |<span data-ttu-id="08332-112">Value</span><span class="sxs-lookup"><span data-stu-id="08332-112">Value</span></span>  |<span data-ttu-id="08332-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08332-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="08332-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="08332-114">0x80041001</span></span> | <span data-ttu-id="08332-115">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="08332-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="08332-116">0</span><span class="sxs-lookup"><span data-stu-id="08332-116">0</span></span> | <span data-ttu-id="08332-117">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="08332-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="08332-118">Note</span><span class="sxs-lookup"><span data-stu-id="08332-118">Remarks</span></span>

<span data-ttu-id="08332-119">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="08332-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="08332-120">Una chiamata alla funzione `EndEnumeration` non è obbligatoria, ma è consigliabile perché rilascia le risorse associate all'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="08332-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="08332-121">Tuttavia, le risorse vengono deallocate automaticamente quando viene avviata l'enumerazione successiva o l'oggetto viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="08332-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="08332-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08332-122">Requirements</span></span>

<span data-ttu-id="08332-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08332-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="08332-124">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="08332-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="08332-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="08332-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="08332-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08332-126">See also</span></span>

- [<span data-ttu-id="08332-127">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="08332-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
