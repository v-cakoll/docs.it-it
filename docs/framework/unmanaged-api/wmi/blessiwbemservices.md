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
ms.openlocfilehash: a65c3c14507b2520c69875a1bc101ce826ace7ba
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532165"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="04439-103">BlessIWbemServices (funzione)</span><span class="sxs-lookup"><span data-stu-id="04439-103">BlessIWbemServices function</span></span>
<span data-ttu-id="04439-104">Indica se le credenziali utente di consentono l'accesso all'oggetto specificato [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) classe.</span><span class="sxs-lookup"><span data-stu-id="04439-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="04439-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04439-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="04439-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="04439-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="04439-107">[in] Un puntatore per il [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) oggetto per cui sono necessarie le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="04439-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="04439-108">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="04439-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="04439-109">[in] La password associata `strUser`.</span><span class="sxs-lookup"><span data-stu-id="04439-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="04439-110">`strAuthority` [in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="04439-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="04439-111">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="04439-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="04439-112">`impLevel` [in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="04439-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="04439-113">`authnLevel` [in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="04439-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="04439-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="04439-114">Return value</span></span>

<span data-ttu-id="04439-115">I seguenti valori restituiti da questa funzione sono definiti nel *Winerror* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="04439-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="04439-116">Costante</span><span class="sxs-lookup"><span data-stu-id="04439-116">Constant</span></span>  |<span data-ttu-id="04439-117">Valore</span><span class="sxs-lookup"><span data-stu-id="04439-117">Value</span></span>  |<span data-ttu-id="04439-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04439-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="04439-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="04439-119">0x80070057</span></span> | <span data-ttu-id="04439-120">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="04439-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="04439-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="04439-121">0x80004003</span></span> | <span data-ttu-id="04439-122">`pIWbemServices` è `null`.</span><span class="sxs-lookup"><span data-stu-id="04439-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="04439-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="04439-123">0x80000008</span></span> | <span data-ttu-id="04439-124">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="04439-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="04439-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="04439-125">0x80000002</span></span> | <span data-ttu-id="04439-126">Memoria disponibile è insufficiente per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="04439-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="04439-127">0</span><span class="sxs-lookup"><span data-stu-id="04439-127">0</span></span> | <span data-ttu-id="04439-128">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="04439-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="04439-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04439-129">Requirements</span></span>  
 <span data-ttu-id="04439-130">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04439-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04439-131">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="04439-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="04439-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04439-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04439-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04439-133">See also</span></span>  
[<span data-ttu-id="04439-134">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="04439-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
