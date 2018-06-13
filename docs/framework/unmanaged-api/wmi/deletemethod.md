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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd862910d0c9bb0274158c2c516211cef598a553
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457808"
---
# <a name="deletemethod-function"></a><span data-ttu-id="b7ea3-103">Funzione DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="b7ea3-103">DeleteMethod function</span></span>
<span data-ttu-id="b7ea3-104">Elimina il metodo specificato da una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b7ea3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7ea3-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="b7ea3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7ea3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b7ea3-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b7ea3-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="b7ea3-109">[in] Il nome del metodo da rimuovere dalla tabella della classe.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="b7ea3-110">`wszName` deve essere un puntatore a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b7ea3-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b7ea3-111">Return value</span></span>

<span data-ttu-id="b7ea3-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="b7ea3-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b7ea3-113">Costante</span><span class="sxs-lookup"><span data-stu-id="b7ea3-113">Constant</span></span>  |<span data-ttu-id="b7ea3-114">Valore</span><span class="sxs-lookup"><span data-stu-id="b7ea3-114">Value</span></span>  |<span data-ttu-id="b7ea3-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7ea3-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="b7ea3-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b7ea3-116">0x80041002</span></span> | <span data-ttu-id="b7ea3-117">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b7ea3-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b7ea3-118">0x80041006</span></span> | <span data-ttu-id="b7ea3-119">Non è disponibile memoria sufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b7ea3-120">0</span><span class="sxs-lookup"><span data-stu-id="b7ea3-120">0</span></span> | <span data-ttu-id="b7ea3-121">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b7ea3-122">Note</span><span class="sxs-lookup"><span data-stu-id="b7ea3-122">Remarks</span></span>

<span data-ttu-id="b7ea3-123">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b7ea3-124">L'eliminazione di metodo non è supportata per [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) puntatori che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="b7ea3-124">Method deletion is not supported for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7ea3-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7ea3-125">Requirements</span></span>  
 <span data-ttu-id="b7ea3-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ea3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ea3-127">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b7ea3-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b7ea3-128">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ea3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ea3-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7ea3-129">See also</span></span>  
[<span data-ttu-id="b7ea3-130">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b7ea3-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
