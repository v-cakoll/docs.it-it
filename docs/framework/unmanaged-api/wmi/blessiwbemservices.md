---
title: Funzione BlessIWbemServices (riferimenti alle API non gestite)
description: La funzione BlessIWbemServices indica se le credenziali utente consentono l'accesso a una classe IWbemServices.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BlessIWbemServices
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BlessIWbemServices
helpviewer_keywords: BlessIWbemServices function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67431d4272ac1da4d400a5552c61cf464680b502
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="541f0-103">BlessIWbemServices (funzione)</span><span class="sxs-lookup"><span data-stu-id="541f0-103">BlessIWbemServices function</span></span>
<span data-ttu-id="541f0-104">Indica se le credenziali utente di consentono l'accesso all'oggetto specificato [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) classe.</span><span class="sxs-lookup"><span data-stu-id="541f0-104">Indicates whether the user credentials permit access to the specified [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="541f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="541f0-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="541f0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="541f0-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="541f0-107">[in] Un puntatore al [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) oggetto per cui sono necessarie le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="541f0-107">[in] A pointer to the [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="541f0-108">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="541f0-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="541f0-109">[in] La password associata a `strUser`.</span><span class="sxs-lookup"><span data-stu-id="541f0-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="541f0-110">`strAuthority`[in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="541f0-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="541f0-111">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="541f0-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="541f0-112">`impLevel`[in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="541f0-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="541f0-113">`authnLevel`[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="541f0-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="541f0-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="541f0-114">Return value</span></span>

<span data-ttu-id="541f0-115">I seguenti valori restituiti da questa funzione sono definiti nel *Winerror* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="541f0-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="541f0-116">Costante</span><span class="sxs-lookup"><span data-stu-id="541f0-116">Constant</span></span>  |<span data-ttu-id="541f0-117">Valore</span><span class="sxs-lookup"><span data-stu-id="541f0-117">Value</span></span>  |<span data-ttu-id="541f0-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="541f0-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="541f0-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="541f0-119">0x80070057</span></span> | <span data-ttu-id="541f0-120">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="541f0-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="541f0-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="541f0-121">0x80004003</span></span> | <span data-ttu-id="541f0-122">`pIWbemServices` è `null`.</span><span class="sxs-lookup"><span data-stu-id="541f0-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="541f0-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="541f0-123">0x80000008</span></span> | <span data-ttu-id="541f0-124">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="541f0-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="541f0-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="541f0-125">0x80000002</span></span> | <span data-ttu-id="541f0-126">Memoria disponibile è insufficiente per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="541f0-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="541f0-127">0</span><span class="sxs-lookup"><span data-stu-id="541f0-127">0</span></span> | <span data-ttu-id="541f0-128">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="541f0-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="541f0-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="541f0-129">Requirements</span></span>  
 <span data-ttu-id="541f0-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="541f0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="541f0-131">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="541f0-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="541f0-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="541f0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="541f0-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="541f0-133">See also</span></span>  
[<span data-ttu-id="541f0-134">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="541f0-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
