---
title: Funzione CreateClassEnumWmi (riferimenti alle API non gestite)
description: La funzione CreateClassEnumWmi restituisce un enumeratore per tutte le classi che soddisfano i criteri specificati.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1d637479bd140e635ee647a1e30d03343d8b0dcd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107524"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="451f7-103">CreateClassEnumWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="451f7-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="451f7-104">Restituisce un enumeratore per tutte le classi che soddisfano i criteri di selezione specificati.</span><span class="sxs-lookup"><span data-stu-id="451f7-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="451f7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="451f7-105">Syntax</span></span>

```cpp
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="451f7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="451f7-106">Parameters</span></span>

`strSuperclass`\
<span data-ttu-id="451f7-107">in Se non `null` o vuoto, specifica il nome di una classe padre. l'enumeratore restituisce solo le sottoclassi di questa classe.</span><span class="sxs-lookup"><span data-stu-id="451f7-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="451f7-108">Se è `null` o vuoto e `lFlags` è WBEM_FLAG_SHALLOW, restituisce solo le classi di primo livello (classi senza classe padre).</span><span class="sxs-lookup"><span data-stu-id="451f7-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="451f7-109">Se è `null` o vuoto e `lFlags` è `WBEM_FLAG_DEEP`, restituisce tutte le classi nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="451f7-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`\
<span data-ttu-id="451f7-110">in Combinazione di flag che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="451f7-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="451f7-111">I valori seguenti vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="451f7-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="451f7-112">Costante</span><span class="sxs-lookup"><span data-stu-id="451f7-112">Constant</span></span>  |<span data-ttu-id="451f7-113">Value</span><span class="sxs-lookup"><span data-stu-id="451f7-113">Value</span></span>  |<span data-ttu-id="451f7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="451f7-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="451f7-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="451f7-115">0x20000</span></span> | <span data-ttu-id="451f7-116">Se impostata, la funzione recupera i qualificatori modificati archiviati nello spazio dei nomi localizzato delle impostazioni locali della connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="451f7-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="451f7-117">Se non è impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato.</span><span class="sxs-lookup"><span data-stu-id="451f7-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="451f7-118">0</span><span class="sxs-lookup"><span data-stu-id="451f7-118">0</span></span> | <span data-ttu-id="451f7-119">L'enumerazione include tutte le sottoclassi nella gerarchia, ma non questa classe.</span><span class="sxs-lookup"><span data-stu-id="451f7-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="451f7-120">1</span><span class="sxs-lookup"><span data-stu-id="451f7-120">1</span></span> | <span data-ttu-id="451f7-121">L'enumerazione include solo le istanze pure di questa classe ed esclude tutte le istanze delle sottoclassi che forniscono proprietà non trovate in questa classe.</span><span class="sxs-lookup"><span data-stu-id="451f7-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="451f7-122">0x10</span><span class="sxs-lookup"><span data-stu-id="451f7-122">0x10</span></span> | <span data-ttu-id="451f7-123">Il flag causa una chiamata semisincrono.</span><span class="sxs-lookup"><span data-stu-id="451f7-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="451f7-124">0x20</span><span class="sxs-lookup"><span data-stu-id="451f7-124">0x20</span></span> | <span data-ttu-id="451f7-125">La funzione restituisce un enumeratore di sola trasmissione.</span><span class="sxs-lookup"><span data-stu-id="451f7-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="451f7-126">In genere, gli enumeratori di sola trasmissione sono più veloci e utilizzano meno memoria rispetto agli enumeratori convenzionali, ma non consentono le chiamate da [clonare](clone.md).</span><span class="sxs-lookup"><span data-stu-id="451f7-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="451f7-127">0</span><span class="sxs-lookup"><span data-stu-id="451f7-127">0</span></span> | <span data-ttu-id="451f7-128">WMI mantiene i puntatori agli oggetti nell'enumerazione fino a quando non vengono rilasciati.</span><span class="sxs-lookup"><span data-stu-id="451f7-128">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="451f7-129">I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="451f7-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="451f7-130">in In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="451f7-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="451f7-131">In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce le classi richieste.</span><span class="sxs-lookup"><span data-stu-id="451f7-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="451f7-132">out Riceve il puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="451f7-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="451f7-133">in Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="451f7-133">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="451f7-134">in Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="451f7-134">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="451f7-135">in Puntatore a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) che rappresenta lo spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="451f7-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="451f7-136">in Nome utente.</span><span class="sxs-lookup"><span data-stu-id="451f7-136">[in] The user name.</span></span> <span data-ttu-id="451f7-137">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="451f7-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="451f7-138">in Password.</span><span class="sxs-lookup"><span data-stu-id="451f7-138">[in] The password.</span></span> <span data-ttu-id="451f7-139">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="451f7-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="451f7-140">in Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="451f7-140">[in] The domain name of the user.</span></span> <span data-ttu-id="451f7-141">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="451f7-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="451f7-142">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="451f7-142">Return value</span></span>

<span data-ttu-id="451f7-143">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="451f7-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="451f7-144">Costante</span><span class="sxs-lookup"><span data-stu-id="451f7-144">Constant</span></span>  |<span data-ttu-id="451f7-145">Value</span><span class="sxs-lookup"><span data-stu-id="451f7-145">Value</span></span>  |<span data-ttu-id="451f7-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="451f7-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="451f7-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="451f7-147">0x80041003</span></span> | <span data-ttu-id="451f7-148">L'utente non dispone delle autorizzazioni necessarie per visualizzare una o più classi che la funzione può restituire.</span><span class="sxs-lookup"><span data-stu-id="451f7-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="451f7-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="451f7-149">0x80041001</span></span> | <span data-ttu-id="451f7-150">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="451f7-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="451f7-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="451f7-151">0x80041010</span></span> | <span data-ttu-id="451f7-152">`strSuperClass` non esiste.</span><span class="sxs-lookup"><span data-stu-id="451f7-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="451f7-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="451f7-153">0x80041008</span></span> | <span data-ttu-id="451f7-154">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="451f7-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="451f7-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="451f7-155">0x80041006</span></span> | <span data-ttu-id="451f7-156">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="451f7-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="451f7-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="451f7-157">0x80041033</span></span> | <span data-ttu-id="451f7-158">WMI è stato probabilmente interrotto e riavviato.</span><span class="sxs-lookup"><span data-stu-id="451f7-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="451f7-159">Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="451f7-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="451f7-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="451f7-160">0x80041015</span></span> | <span data-ttu-id="451f7-161">Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="451f7-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="451f7-162">0</span><span class="sxs-lookup"><span data-stu-id="451f7-162">0</span></span> | <span data-ttu-id="451f7-163">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="451f7-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="451f7-164">Note</span><span class="sxs-lookup"><span data-stu-id="451f7-164">Remarks</span></span>

<span data-ttu-id="451f7-165">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices:: CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) .</span><span class="sxs-lookup"><span data-stu-id="451f7-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="451f7-166">Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="451f7-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="451f7-167">Requisiti</span><span class="sxs-lookup"><span data-stu-id="451f7-167">Requirements</span></span>

<span data-ttu-id="451f7-168">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="451f7-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="451f7-169">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="451f7-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="451f7-170">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="451f7-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="451f7-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="451f7-171">See also</span></span>

- [<span data-ttu-id="451f7-172">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="451f7-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
