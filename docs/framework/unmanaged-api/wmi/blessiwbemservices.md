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
ms.openlocfilehash: 4b15af840cc00b3ec261604db4f3625c6b975d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176864"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="2d65e-103">Funzione BlessIWbemServices</span><span class="sxs-lookup"><span data-stu-id="2d65e-103">BlessIWbemServices function</span></span>
<span data-ttu-id="2d65e-104">Indica se le credenziali utente consentono l'accesso alla classe [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) specificata.</span><span class="sxs-lookup"><span data-stu-id="2d65e-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2d65e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d65e-105">Syntax</span></span>  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="2d65e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d65e-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="2d65e-107">[in] Puntatore all'oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) per cui sono necessarie autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2d65e-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`\
<span data-ttu-id="2d65e-108">[in] Nome utente.</span><span class="sxs-lookup"><span data-stu-id="2d65e-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="2d65e-109">[in] La password `strUser`associata a .</span><span class="sxs-lookup"><span data-stu-id="2d65e-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="2d65e-110">[in] Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2d65e-110">[in] The domain name of the user.</span></span> <span data-ttu-id="2d65e-111">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="2d65e-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="2d65e-112">[in] Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="2d65e-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="2d65e-113">[in] Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d65e-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="2d65e-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2d65e-114">Return value</span></span>

<span data-ttu-id="2d65e-115">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione WinError.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="2d65e-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2d65e-116">Costante</span><span class="sxs-lookup"><span data-stu-id="2d65e-116">Constant</span></span>  |<span data-ttu-id="2d65e-117">valore</span><span class="sxs-lookup"><span data-stu-id="2d65e-117">Value</span></span>  |<span data-ttu-id="2d65e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d65e-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="2d65e-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="2d65e-119">0x80070057</span></span> | <span data-ttu-id="2d65e-120">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="2d65e-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="2d65e-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="2d65e-121">0x80004003</span></span> | <span data-ttu-id="2d65e-122">`pIWbemServices` è `null`.</span><span class="sxs-lookup"><span data-stu-id="2d65e-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="2d65e-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="2d65e-123">0x80000008</span></span> | <span data-ttu-id="2d65e-124">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="2d65e-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="2d65e-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="2d65e-125">0x80000002</span></span> | <span data-ttu-id="2d65e-126">Memoria insufficiente per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="2d65e-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="2d65e-127">0</span><span class="sxs-lookup"><span data-stu-id="2d65e-127">0</span></span> | <span data-ttu-id="2d65e-128">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2d65e-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="2d65e-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d65e-129">Requirements</span></span>  

 <span data-ttu-id="2d65e-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d65e-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d65e-131">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2d65e-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2d65e-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d65e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d65e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d65e-133">See also</span></span>

- [<span data-ttu-id="2d65e-134">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="2d65e-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
