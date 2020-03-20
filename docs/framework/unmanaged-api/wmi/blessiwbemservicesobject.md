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
ms.openlocfilehash: fd822f78d29ad3a75fb5e57dd7c23b7049d445b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175031"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="61e91-103">Funzione BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="61e91-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="61e91-104">Indica se le credenziali utente consentono l'accesso a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) specificato.</span><span class="sxs-lookup"><span data-stu-id="61e91-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="61e91-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61e91-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="61e91-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="61e91-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="61e91-107">[in] Puntatore a un oggetto servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="61e91-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="61e91-108">[in] Nome utente.</span><span class="sxs-lookup"><span data-stu-id="61e91-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="61e91-109">[in] La password `strUser`associata a .</span><span class="sxs-lookup"><span data-stu-id="61e91-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="61e91-110">[in] Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="61e91-110">[in] The domain name of the user.</span></span> <span data-ttu-id="61e91-111">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="61e91-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="61e91-112">[in] Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="61e91-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="61e91-113">[in] Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="61e91-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="61e91-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="61e91-114">Return value</span></span>

<span data-ttu-id="61e91-115">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione WinError.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="61e91-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="61e91-116">Costante</span><span class="sxs-lookup"><span data-stu-id="61e91-116">Constant</span></span>  |<span data-ttu-id="61e91-117">valore</span><span class="sxs-lookup"><span data-stu-id="61e91-117">Value</span></span>  |<span data-ttu-id="61e91-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61e91-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="61e91-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="61e91-119">0x80070057</span></span> | <span data-ttu-id="61e91-120">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="61e91-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="61e91-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="61e91-121">0x80004003</span></span> | <span data-ttu-id="61e91-122">`pIWbemServices` è `null`.</span><span class="sxs-lookup"><span data-stu-id="61e91-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="61e91-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="61e91-123">0x80000008</span></span> | <span data-ttu-id="61e91-124">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="61e91-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="61e91-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="61e91-125">0x80000002</span></span> | <span data-ttu-id="61e91-126">Memoria insufficiente per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="61e91-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="61e91-127">0</span><span class="sxs-lookup"><span data-stu-id="61e91-127">0</span></span> | <span data-ttu-id="61e91-128">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="61e91-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="61e91-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61e91-129">Requirements</span></span>

 <span data-ttu-id="61e91-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61e91-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="61e91-131">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="61e91-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="61e91-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="61e91-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="61e91-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61e91-133">See also</span></span>

- [<span data-ttu-id="61e91-134">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="61e91-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
