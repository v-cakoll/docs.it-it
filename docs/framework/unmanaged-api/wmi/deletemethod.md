---
title: Funzione DeleteMethod (riferimenti alle API non gestite)
description: La funzione DeleteMethod Elimina il metodo specificato da una definizione di classe CIM.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: db360584dacf250be2f35e5e6666f8332b39a8dd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120656"
---
# <a name="deletemethod-function"></a><span data-ttu-id="b52f4-103">Funzione DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="b52f4-103">DeleteMethod function</span></span>
<span data-ttu-id="b52f4-104">Elimina il metodo specificato da una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="b52f4-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b52f4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b52f4-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="b52f4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b52f4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b52f4-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="b52f4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b52f4-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="b52f4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="b52f4-109">in Nome del metodo da rimuovere dalla tabella della classe.</span><span class="sxs-lookup"><span data-stu-id="b52f4-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="b52f4-110">`wszName` deve essere un puntatore a una `LPCWSTR`valida.</span><span class="sxs-lookup"><span data-stu-id="b52f4-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b52f4-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b52f4-111">Return value</span></span>

<span data-ttu-id="b52f4-112">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="b52f4-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b52f4-113">Costante</span><span class="sxs-lookup"><span data-stu-id="b52f4-113">Constant</span></span>  |<span data-ttu-id="b52f4-114">Value</span><span class="sxs-lookup"><span data-stu-id="b52f4-114">Value</span></span>  |<span data-ttu-id="b52f4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b52f4-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="b52f4-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b52f4-116">0x80041002</span></span> | <span data-ttu-id="b52f4-117">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="b52f4-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b52f4-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b52f4-118">0x80041006</span></span> | <span data-ttu-id="b52f4-119">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="b52f4-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b52f4-120">0</span><span class="sxs-lookup"><span data-stu-id="b52f4-120">0</span></span> | <span data-ttu-id="b52f4-121">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b52f4-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b52f4-122">Note</span><span class="sxs-lookup"><span data-stu-id="b52f4-122">Remarks</span></span>

<span data-ttu-id="b52f4-123">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::D eletemethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) .</span><span class="sxs-lookup"><span data-stu-id="b52f4-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="b52f4-124">L'eliminazione del metodo non è supportata per i puntatori [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="b52f4-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="b52f4-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b52f4-125">Requirements</span></span>  
 <span data-ttu-id="b52f4-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b52f4-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b52f4-127">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="b52f4-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b52f4-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b52f4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52f4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b52f4-129">See also</span></span>

- [<span data-ttu-id="b52f4-130">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b52f4-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
