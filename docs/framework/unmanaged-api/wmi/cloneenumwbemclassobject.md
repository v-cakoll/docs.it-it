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
ms.openlocfilehash: 52edc72e3714ceaf8cc92f272da6a374eb324dad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661646"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="6784e-103">CloneEnumWbemClassObject (funzione)</span><span class="sxs-lookup"><span data-stu-id="6784e-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="6784e-104">Crea una copia logica di un enumeratore mantenendone la posizione corrente in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6784e-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6784e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6784e-105">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="6784e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6784e-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="6784e-107">[out] Riceve un puntatore a una nuova [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="6784e-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`  
<span data-ttu-id="6784e-108">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="6784e-108">[in] The authorization level.</span></span>

<span data-ttu-id="6784e-109">`impLevel` [in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="6784e-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="6784e-110">[out] Un puntatore per il [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) istanza da duplicare.</span><span class="sxs-lookup"><span data-stu-id="6784e-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="6784e-111">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="6784e-111">[in] The user name.</span></span> <span data-ttu-id="6784e-112">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="6784e-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="6784e-113">[in] La password.</span><span class="sxs-lookup"><span data-stu-id="6784e-113">[in] The password.</span></span> <span data-ttu-id="6784e-114">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="6784e-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="6784e-115">[in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6784e-115">[in] The domain name of the user.</span></span> <span data-ttu-id="6784e-116">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="6784e-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="6784e-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6784e-117">Return value</span></span>

<span data-ttu-id="6784e-118">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="6784e-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6784e-119">Costante</span><span class="sxs-lookup"><span data-stu-id="6784e-119">Constant</span></span>  |<span data-ttu-id="6784e-120">Value</span><span class="sxs-lookup"><span data-stu-id="6784e-120">Value</span></span>  |<span data-ttu-id="6784e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6784e-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="6784e-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6784e-122">0x80041001</span></span> | <span data-ttu-id="6784e-123">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="6784e-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6784e-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6784e-124">0x80041008</span></span> | <span data-ttu-id="6784e-125">Un parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="6784e-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6784e-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6784e-126">0x80041006</span></span> | <span data-ttu-id="6784e-127">È disponibile insufficiente memoria completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="6784e-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="6784e-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="6784e-128">0x80041015</span></span> | <span data-ttu-id="6784e-129">Il collegamento di remote procedure call (RPC) tra il processo corrente e WMI non riuscita.</span><span class="sxs-lookup"><span data-stu-id="6784e-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6784e-130">0</span><span class="sxs-lookup"><span data-stu-id="6784e-130">0</span></span> | <span data-ttu-id="6784e-131">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="6784e-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6784e-132">Note</span><span class="sxs-lookup"><span data-stu-id="6784e-132">Remarks</span></span>

<span data-ttu-id="6784e-133">Questa funzione esegue il wrapping di una chiamata per il [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) (metodo).</span><span class="sxs-lookup"><span data-stu-id="6784e-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="6784e-134">Questo metodo esegue solo una copia "best effort".</span><span class="sxs-lookup"><span data-stu-id="6784e-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="6784e-135">A causa della natura dinamica del numero di oggetti CIM, è possibile che il nuovo enumeratore non enumera lo stesso set di oggetti l'enumeratore di origine.</span><span class="sxs-lookup"><span data-stu-id="6784e-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="6784e-136">Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="6784e-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="6784e-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="6784e-137">Example</span></span>

<span data-ttu-id="6784e-138">Per un esempio, vedere la [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) (metodo).</span><span class="sxs-lookup"><span data-stu-id="6784e-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6784e-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6784e-139">Requirements</span></span>  
 <span data-ttu-id="6784e-140">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6784e-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6784e-141">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6784e-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6784e-142">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6784e-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6784e-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6784e-143">See also</span></span>
- [<span data-ttu-id="6784e-144">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="6784e-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
