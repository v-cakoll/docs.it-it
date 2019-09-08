---
title: Funzione CloneEnumWbemClassObject (riferimenti alle API non gestite)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1605314f94fd82d2a2cd7be105dde9e273f607bc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798693"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="866bf-103">Funzione CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="866bf-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="866bf-104">Crea una copia logica di un enumeratore mantenendone la posizione corrente in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="866bf-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="866bf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="866bf-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="866bf-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="866bf-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="866bf-107">out Riceve un puntatore a un nuovo [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="866bf-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="866bf-108">in Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="866bf-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="866bf-109">in Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="866bf-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="866bf-110">out Puntatore all'istanza di [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) da clonare.</span><span class="sxs-lookup"><span data-stu-id="866bf-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="866bf-111">in Nome utente.</span><span class="sxs-lookup"><span data-stu-id="866bf-111">[in] The user name.</span></span> <span data-ttu-id="866bf-112">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="866bf-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="866bf-113">in Password.</span><span class="sxs-lookup"><span data-stu-id="866bf-113">[in] The password.</span></span> <span data-ttu-id="866bf-114">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="866bf-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="866bf-115">`strAuthority`[in] nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="866bf-115">`strAuthority`\ [in] The domain name of the user.</span></span> <span data-ttu-id="866bf-116">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="866bf-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="866bf-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="866bf-117">Return value</span></span>

<span data-ttu-id="866bf-118">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="866bf-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="866bf-119">Costante</span><span class="sxs-lookup"><span data-stu-id="866bf-119">Constant</span></span>  |<span data-ttu-id="866bf-120">Value</span><span class="sxs-lookup"><span data-stu-id="866bf-120">Value</span></span>  |<span data-ttu-id="866bf-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="866bf-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="866bf-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="866bf-122">0x80041001</span></span> | <span data-ttu-id="866bf-123">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="866bf-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="866bf-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="866bf-124">0x80041008</span></span> | <span data-ttu-id="866bf-125">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="866bf-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="866bf-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="866bf-126">0x80041006</span></span> | <span data-ttu-id="866bf-127">La memoria disponibile non è sufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="866bf-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="866bf-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="866bf-128">0x80041015</span></span> | <span data-ttu-id="866bf-129">Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="866bf-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="866bf-130">0</span><span class="sxs-lookup"><span data-stu-id="866bf-130">0</span></span> | <span data-ttu-id="866bf-131">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="866bf-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="866bf-132">Note</span><span class="sxs-lookup"><span data-stu-id="866bf-132">Remarks</span></span>

<span data-ttu-id="866bf-133">Questa funzione esegue il wrapping di una chiamata al metodo [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="866bf-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="866bf-134">Questo metodo esegue solo una copia "Best Effort".</span><span class="sxs-lookup"><span data-stu-id="866bf-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="866bf-135">A causa della natura dinamica di molti oggetti CIM, è possibile che il nuovo enumeratore non enumera lo stesso set di oggetti dell'enumeratore di origine.</span><span class="sxs-lookup"><span data-stu-id="866bf-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="866bf-136">Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="866bf-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="866bf-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="866bf-137">Example</span></span>

<span data-ttu-id="866bf-138">Per un esempio, vedere il metodo [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="866bf-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="866bf-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="866bf-139">Requirements</span></span>
 <span data-ttu-id="866bf-140">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="866bf-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="866bf-141">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="866bf-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="866bf-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="866bf-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="866bf-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="866bf-143">See also</span></span>

- [<span data-ttu-id="866bf-144">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="866bf-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
