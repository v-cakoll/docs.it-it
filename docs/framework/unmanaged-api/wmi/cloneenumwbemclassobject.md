---
title: Funzione CloneEnumWbemClassObject (riferimenti all'API non gestita)
description: La funzione CloneEnumWbemClassObject crea una copia logica di un enumeratore.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175018"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="ba6bd-103">Funzione CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="ba6bd-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="ba6bd-104">Crea una copia logica di un enumeratore mantenendone la posizione corrente in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ba6bd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba6bd-105">Syntax</span></span>

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum,
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject,
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="ba6bd-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba6bd-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="ba6bd-107">[fuori] Riceve un puntatore a un nuovo [oggetto IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="ba6bd-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="ba6bd-108">[in] Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="ba6bd-109">[in] Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="ba6bd-110">[fuori] Puntatore all'istanza di [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) da clonare.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="ba6bd-111">[in] Nome utente.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-111">[in] The user name.</span></span> <span data-ttu-id="ba6bd-112">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="ba6bd-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="ba6bd-113">[in] La password.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-113">[in] The password.</span></span> <span data-ttu-id="ba6bd-114">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="ba6bd-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="ba6bd-115">[in] Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-115">[in] The domain name of the user.</span></span> <span data-ttu-id="ba6bd-116">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="ba6bd-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="ba6bd-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba6bd-117">Return value</span></span>

<span data-ttu-id="ba6bd-118">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="ba6bd-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ba6bd-119">Costante</span><span class="sxs-lookup"><span data-stu-id="ba6bd-119">Constant</span></span>  |<span data-ttu-id="ba6bd-120">valore</span><span class="sxs-lookup"><span data-stu-id="ba6bd-120">Value</span></span>  |<span data-ttu-id="ba6bd-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba6bd-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ba6bd-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ba6bd-122">0x80041001</span></span> | <span data-ttu-id="ba6bd-123">C'è stato un fallimento generale.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ba6bd-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ba6bd-124">0x80041008</span></span> | <span data-ttu-id="ba6bd-125">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ba6bd-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ba6bd-126">0x80041006</span></span> | <span data-ttu-id="ba6bd-127">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ba6bd-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ba6bd-128">0x80041015</span></span> | <span data-ttu-id="ba6bd-129">Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ba6bd-130">0</span><span class="sxs-lookup"><span data-stu-id="ba6bd-130">0</span></span> | <span data-ttu-id="ba6bd-131">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ba6bd-132">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ba6bd-132">Remarks</span></span>

<span data-ttu-id="ba6bd-133">Questa funzione esegue il wrapping di una chiamata al metodo [IEnumWbemClassObject::Clone.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)</span><span class="sxs-lookup"><span data-stu-id="ba6bd-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="ba6bd-134">Questo metodo fa solo una copia "migliore sforzo".</span><span class="sxs-lookup"><span data-stu-id="ba6bd-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="ba6bd-135">A causa della natura dinamica di molti oggetti CIM, è possibile che il nuovo enumeratore non enumeri lo stesso set di oggetti dell'enumeratore di origine.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="ba6bd-136">Se la chiamata di funzione ha esito negativo, è possibile ottenere informazioni aggiuntive sull'errore chiamando la funzione [GetErrorInfo.If](geterrorinfo.md) the function call fails, you can obtain additional error information by calling the GetErrorInfo function.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="ba6bd-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba6bd-137">Example</span></span>

<span data-ttu-id="ba6bd-138">Per un esempio, vedere il [metodo IEnumWbemClassObject::Clone.For an example, see the IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span><span class="sxs-lookup"><span data-stu-id="ba6bd-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ba6bd-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba6bd-139">Requirements</span></span>
 <span data-ttu-id="ba6bd-140">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba6bd-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ba6bd-141">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ba6bd-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="ba6bd-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ba6bd-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ba6bd-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba6bd-143">See also</span></span>

- [<span data-ttu-id="ba6bd-144">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ba6bd-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
