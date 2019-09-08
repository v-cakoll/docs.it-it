---
title: Funzione Delete (riferimenti alle API non gestite)
description: La funzione Delete Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1bf9bd5d93d1affee649588138456269411d280
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798678"
---
# <a name="delete-function"></a><span data-ttu-id="c4884-103">Funzione Delete</span><span class="sxs-lookup"><span data-stu-id="c4884-103">Delete function</span></span>

<span data-ttu-id="c4884-104">Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="c4884-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c4884-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4884-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="c4884-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c4884-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="c4884-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="c4884-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="c4884-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="c4884-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="c4884-109">in Nome della proprietà da eliminare.</span><span class="sxs-lookup"><span data-stu-id="c4884-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="c4884-110">`wszName`deve essere un puntatore a un oggetto `LPCWSTR`valido.</span><span class="sxs-lookup"><span data-stu-id="c4884-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c4884-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c4884-111">Return value</span></span>

<span data-ttu-id="c4884-112">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="c4884-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c4884-113">Costante</span><span class="sxs-lookup"><span data-stu-id="c4884-113">Constant</span></span>  |<span data-ttu-id="c4884-114">Value</span><span class="sxs-lookup"><span data-stu-id="c4884-114">Value</span></span>  |<span data-ttu-id="c4884-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4884-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="c4884-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c4884-116">0x80041001</span></span> | <span data-ttu-id="c4884-117">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="c4884-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="c4884-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="c4884-118">0x80041016</span></span> | <span data-ttu-id="c4884-119">Impossibile eliminare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="c4884-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c4884-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c4884-120">0x80041008</span></span> | <span data-ttu-id="c4884-121">`wszName` non è valido.</span><span class="sxs-lookup"><span data-stu-id="c4884-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="c4884-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c4884-122">0x80041002</span></span> | <span data-ttu-id="c4884-123">La proprietà specificata non esiste.</span><span class="sxs-lookup"><span data-stu-id="c4884-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c4884-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c4884-124">0x80041006</span></span> | <span data-ttu-id="c4884-125">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c4884-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="c4884-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="c4884-126">0x8004101c</span></span> | <span data-ttu-id="c4884-127">La proprietà viene ereditata da una classe base.</span><span class="sxs-lookup"><span data-stu-id="c4884-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="c4884-128">La proprietà è una proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="c4884-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c4884-129">0</span><span class="sxs-lookup"><span data-stu-id="c4884-129">0</span></span> | <span data-ttu-id="c4884-130">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c4884-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="c4884-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="c4884-131">0x80041030</span></span> | <span data-ttu-id="c4884-132">La funzione ha eliminato un valore predefinito di override per la classe corrente.</span><span class="sxs-lookup"><span data-stu-id="c4884-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="c4884-133">Il valore predefinito per questa proprietà nella classe padre è stato riattivato.</span><span class="sxs-lookup"><span data-stu-id="c4884-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c4884-134">Note</span><span class="sxs-lookup"><span data-stu-id="c4884-134">Remarks</span></span>

<span data-ttu-id="c4884-135">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::D Elimina](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) .</span><span class="sxs-lookup"><span data-stu-id="c4884-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4884-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4884-136">Requirements</span></span>

<span data-ttu-id="c4884-137">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4884-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c4884-138">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="c4884-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="c4884-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c4884-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c4884-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4884-140">See also</span></span>

- [<span data-ttu-id="c4884-141">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c4884-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
