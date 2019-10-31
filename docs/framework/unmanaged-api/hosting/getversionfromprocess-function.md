---
title: Funzione GetVersionFromProcess
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: 76c033b11f3212241827d74f4fe18ee881f20b64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127041"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="df2e4-102">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="df2e4-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="df2e4-103">Ottiene il numero di versione del Common Language Runtime (CLR) associato all'handle di processo specificato.</span><span class="sxs-lookup"><span data-stu-id="df2e4-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="df2e4-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="df2e4-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df2e4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df2e4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df2e4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="df2e4-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="df2e4-107">in Handle per un processo.</span><span class="sxs-lookup"><span data-stu-id="df2e4-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="df2e4-108">out Buffer contenente la stringa del numero di versione al completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="df2e4-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="df2e4-109">in Lunghezza del buffer della versione.</span><span class="sxs-lookup"><span data-stu-id="df2e4-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="df2e4-110">out Puntatore alla lunghezza della stringa del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="df2e4-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df2e4-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="df2e4-111">Return Value</span></span>  
 <span data-ttu-id="df2e4-112">Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="df2e4-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="df2e4-113">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="df2e4-113">Return code</span></span>|<span data-ttu-id="df2e4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df2e4-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="df2e4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="df2e4-115">S_OK</span></span>|<span data-ttu-id="df2e4-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="df2e4-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="df2e4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="df2e4-117">E_INVALIDARG</span></span>|<span data-ttu-id="df2e4-118">`pVersion` è null e `cchBuffer` non è null o viceversa.</span><span class="sxs-lookup"><span data-stu-id="df2e4-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="df2e4-119">oppure</span><span class="sxs-lookup"><span data-stu-id="df2e4-119">-or-</span></span><br /><br /> <span data-ttu-id="df2e4-120">`hProcess` non è un handle valido per un processo.</span><span class="sxs-lookup"><span data-stu-id="df2e4-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="df2e4-121">oppure</span><span class="sxs-lookup"><span data-stu-id="df2e4-121">-or-</span></span><br /><br /> <span data-ttu-id="df2e4-122">CLR non caricato.</span><span class="sxs-lookup"><span data-stu-id="df2e4-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="df2e4-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="df2e4-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="df2e4-124">`cchBuffer` è null o minore della lunghezza della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="df2e4-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="df2e4-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="df2e4-125">E_NOTIMPL</span></span>|<span data-ttu-id="df2e4-126">Questo metodo non è disponibile nel sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="df2e4-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df2e4-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df2e4-127">Requirements</span></span>  
 <span data-ttu-id="df2e4-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df2e4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df2e4-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df2e4-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df2e4-130">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="df2e4-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df2e4-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df2e4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2e4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df2e4-132">See also</span></span>

- [<span data-ttu-id="df2e4-133">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="df2e4-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="df2e4-134">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="df2e4-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="df2e4-135">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="df2e4-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
