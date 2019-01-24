---
title: Funzione BlessIWbemServices (riferimenti alle API non gestite)
description: La funzione BlessIWbemServices indica se le credenziali utente consentono l'accesso a una classe IWbemServices.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b127c48a300af01c8e7b32d422e42fbc4796420d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716078"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="729bc-103">BlessIWbemServices (funzione)</span><span class="sxs-lookup"><span data-stu-id="729bc-103">BlessIWbemServices function</span></span>
<span data-ttu-id="729bc-104">Indica se le credenziali utente di consentono l'accesso all'oggetto specificato [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) classe.</span><span class="sxs-lookup"><span data-stu-id="729bc-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="729bc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="729bc-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="729bc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="729bc-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="729bc-107">[in] Un puntatore per il [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) oggetto per cui sono necessarie le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="729bc-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="729bc-108">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="729bc-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="729bc-109">[in] La password associata `strUser`.</span><span class="sxs-lookup"><span data-stu-id="729bc-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="729bc-110">`strAuthority` [in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="729bc-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="729bc-111">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="729bc-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="729bc-112">`impLevel` [in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="729bc-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="729bc-113">`authnLevel` [in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="729bc-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="729bc-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="729bc-114">Return value</span></span>

<span data-ttu-id="729bc-115">I seguenti valori restituiti da questa funzione sono definiti nel *Winerror* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="729bc-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="729bc-116">Costante</span><span class="sxs-lookup"><span data-stu-id="729bc-116">Constant</span></span>  |<span data-ttu-id="729bc-117">Value</span><span class="sxs-lookup"><span data-stu-id="729bc-117">Value</span></span>  |<span data-ttu-id="729bc-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="729bc-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="729bc-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="729bc-119">0x80070057</span></span> | <span data-ttu-id="729bc-120">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="729bc-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="729bc-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="729bc-121">0x80004003</span></span> | <span data-ttu-id="729bc-122">`pIWbemServices` è `null`.</span><span class="sxs-lookup"><span data-stu-id="729bc-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="729bc-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="729bc-123">0x80000008</span></span> | <span data-ttu-id="729bc-124">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="729bc-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="729bc-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="729bc-125">0x80000002</span></span> | <span data-ttu-id="729bc-126">Memoria disponibile è insufficiente per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="729bc-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="729bc-127">0</span><span class="sxs-lookup"><span data-stu-id="729bc-127">0</span></span> | <span data-ttu-id="729bc-128">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="729bc-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="729bc-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="729bc-129">Requirements</span></span>  
 <span data-ttu-id="729bc-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="729bc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="729bc-131">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="729bc-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="729bc-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="729bc-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="729bc-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="729bc-133">See also</span></span>
- [<span data-ttu-id="729bc-134">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="729bc-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
