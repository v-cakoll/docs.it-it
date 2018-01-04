---
title: Funzione CloneEnumWbemClassObject (riferimenti alle API non gestite)
description: La funzione CloneEnumWbemClassObject effettua una copia logica di un enumeratore.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CloneEnumWbemClassObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CloneEnumWbemClassObject
helpviewer_keywords: CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22bcf2731ff682bf538858fc66a7a94be7f5d7df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="c0ea6-103">CloneEnumWbemClassObject (funzione)</span><span class="sxs-lookup"><span data-stu-id="c0ea6-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="c0ea6-104">Crea una copia logica di un enumeratore, mantenendo la posizione corrente nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c0ea6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0ea6-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="c0ea6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0ea6-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="c0ea6-107">[out] Riceve un puntatore a un nuovo [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="c0ea6-107">[out] Receives a pointer to a new [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span></span>

`authLevel`  
<span data-ttu-id="c0ea6-108">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-108">[in] The authorization level.</span></span>

<span data-ttu-id="c0ea6-109">`impLevel`[in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="c0ea6-110">[out] Un puntatore al [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) istanza da duplicare.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-110">[out] A pointer to the [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="c0ea6-111">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-111">[in] The user name.</span></span> <span data-ttu-id="c0ea6-112">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="c0ea6-113">[in] La password.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-113">[in] The password.</span></span> <span data-ttu-id="c0ea6-114">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="c0ea6-115">[in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-115">[in] The domain name of the user.</span></span> <span data-ttu-id="c0ea6-116">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="c0ea6-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c0ea6-117">Return value</span></span>

<span data-ttu-id="c0ea6-118">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="c0ea6-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c0ea6-119">Costante</span><span class="sxs-lookup"><span data-stu-id="c0ea6-119">Constant</span></span>  |<span data-ttu-id="c0ea6-120">Valore</span><span class="sxs-lookup"><span data-stu-id="c0ea6-120">Value</span></span>  |<span data-ttu-id="c0ea6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0ea6-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="c0ea6-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c0ea6-122">0x80041001</span></span> | <span data-ttu-id="c0ea6-123">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c0ea6-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c0ea6-124">0x80041008</span></span> | <span data-ttu-id="c0ea6-125">Un parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c0ea6-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c0ea6-126">0x80041006</span></span> | <span data-ttu-id="c0ea6-127">Memoria insufficiente è disponibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="c0ea6-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="c0ea6-128">0x80041015</span></span> | <span data-ttu-id="c0ea6-129">Il collegamento remote procedure call (RPC) tra il processo corrente e WMI non riuscita.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c0ea6-130">0</span><span class="sxs-lookup"><span data-stu-id="c0ea6-130">0</span></span> | <span data-ttu-id="c0ea6-131">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c0ea6-132">Note</span><span class="sxs-lookup"><span data-stu-id="c0ea6-132">Remarks</span></span>

<span data-ttu-id="c0ea6-133">Questa funzione esegue il wrapping di una chiamata al [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-133">This function wraps a call to the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="c0ea6-134">Questo metodo copia solo "best effort".</span><span class="sxs-lookup"><span data-stu-id="c0ea6-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="c0ea6-135">A causa della natura dinamica di molti oggetti CIM, è possibile che il nuovo enumeratore non enumera lo stesso set di oggetti l'enumeratore di origine.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="c0ea6-136">Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="c0ea6-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="c0ea6-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0ea6-137">Example</span></span>

<span data-ttu-id="c0ea6-138">Per un esempio, vedere il [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="c0ea6-138">For an example, see the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0ea6-139">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0ea6-139">Requirements</span></span>  
 <span data-ttu-id="c0ea6-140">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ea6-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ea6-141">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c0ea6-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c0ea6-142">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ea6-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ea6-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0ea6-143">See also</span></span>  
[<span data-ttu-id="c0ea6-144">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c0ea6-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
