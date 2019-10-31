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
ms.openlocfilehash: f77ff394668a235dd63cf0cddf71ea418a28125b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141678"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="84e81-103">Funzione BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="84e81-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="84e81-104">Indica se le credenziali utente consentono l'accesso a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) specificato.</span><span class="sxs-lookup"><span data-stu-id="84e81-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="84e81-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84e81-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="84e81-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="84e81-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="84e81-107">in Puntatore a un oggetto servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="84e81-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="84e81-108">in Nome utente.</span><span class="sxs-lookup"><span data-stu-id="84e81-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="84e81-109">in Password associata a `strUser`.</span><span class="sxs-lookup"><span data-stu-id="84e81-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="84e81-110">in Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="84e81-110">[in] The domain name of the user.</span></span> <span data-ttu-id="84e81-111">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="84e81-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="84e81-112">in Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="84e81-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="84e81-113">in Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="84e81-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="84e81-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="84e81-114">Return value</span></span>

<span data-ttu-id="84e81-115">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *Winerror. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="84e81-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="84e81-116">Costante</span><span class="sxs-lookup"><span data-stu-id="84e81-116">Constant</span></span>  |<span data-ttu-id="84e81-117">Value</span><span class="sxs-lookup"><span data-stu-id="84e81-117">Value</span></span>  |<span data-ttu-id="84e81-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84e81-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="84e81-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="84e81-119">0x80070057</span></span> | <span data-ttu-id="84e81-120">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="84e81-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="84e81-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="84e81-121">0x80004003</span></span> | <span data-ttu-id="84e81-122">`pIWbemServices` è `null`.</span><span class="sxs-lookup"><span data-stu-id="84e81-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="84e81-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="84e81-123">0x80000008</span></span> | <span data-ttu-id="84e81-124">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="84e81-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="84e81-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="84e81-125">0x80000002</span></span> | <span data-ttu-id="84e81-126">Memoria insufficiente per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="84e81-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="84e81-127">0</span><span class="sxs-lookup"><span data-stu-id="84e81-127">0</span></span> | <span data-ttu-id="84e81-128">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="84e81-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="84e81-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84e81-129">Requirements</span></span>

 <span data-ttu-id="84e81-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e81-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="84e81-131">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="84e81-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="84e81-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="84e81-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="84e81-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84e81-133">See also</span></span>

- [<span data-ttu-id="84e81-134">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="84e81-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
