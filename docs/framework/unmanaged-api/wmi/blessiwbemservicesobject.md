---
title: Funzione BlessIWbemServicesObject (riferimenti alle API non gestite)
description: La funzione BlessIWbemServicesObject indica se le credenziali utente consentono l'accesso a un oggetto IWbemServices
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94c6f47e67cf22f189719a8a9f56e830ee90227c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798722"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="1cbe6-103">Funzione BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="1cbe6-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="1cbe6-104">Indica se le credenziali utente consentono l'accesso a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) specificato.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1cbe6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cbe6-105">Syntax</span></span>

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="1cbe6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1cbe6-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="1cbe6-107">in Puntatore a un oggetto servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="1cbe6-108">in Nome utente.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="1cbe6-109">in Password associata a `strUser`.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="1cbe6-110">in Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-110">[in] The domain name of the user.</span></span> <span data-ttu-id="1cbe6-111">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="1cbe6-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="1cbe6-112">in Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="1cbe6-113">in Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="1cbe6-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1cbe6-114">Return value</span></span>

<span data-ttu-id="1cbe6-115">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *Winerror. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="1cbe6-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1cbe6-116">Costante</span><span class="sxs-lookup"><span data-stu-id="1cbe6-116">Constant</span></span>  |<span data-ttu-id="1cbe6-117">Value</span><span class="sxs-lookup"><span data-stu-id="1cbe6-117">Value</span></span>  |<span data-ttu-id="1cbe6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cbe6-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="1cbe6-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="1cbe6-119">0x80070057</span></span> | <span data-ttu-id="1cbe6-120">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="1cbe6-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="1cbe6-121">0x80004003</span></span> | <span data-ttu-id="1cbe6-122">`pIWbemServices` è `null`.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="1cbe6-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="1cbe6-123">0x80000008</span></span> | <span data-ttu-id="1cbe6-124">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="1cbe6-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="1cbe6-125">0x80000002</span></span> | <span data-ttu-id="1cbe6-126">Memoria insufficiente per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="1cbe6-127">0</span><span class="sxs-lookup"><span data-stu-id="1cbe6-127">0</span></span> | <span data-ttu-id="1cbe6-128">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1cbe6-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="1cbe6-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1cbe6-129">Requirements</span></span>

 <span data-ttu-id="1cbe6-130">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cbe6-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="1cbe6-131">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="1cbe6-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="1cbe6-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1cbe6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1cbe6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cbe6-133">See also</span></span>

- [<span data-ttu-id="1cbe6-134">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1cbe6-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
