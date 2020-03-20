---
title: Funzione GetRequestedRuntimeVersion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 6be0bc5d08f612dcb8ed7d256711e0c4367b9274
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178144"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="ee4d0-102">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="ee4d0-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="ee4d0-103">Ottiene il numero di versione di Common Language Runtime (CLR) richiesto dall'applicazione specificata.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="ee4d0-104">Se tale versione non è installata, ottiene la versione più recente installata prima della versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="ee4d0-105">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee4d0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee4d0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee4d0-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee4d0-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="ee4d0-108">[in] Nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="ee4d0-109">[fuori] Un buffer che contiene la stringa del numero di versione al completamento.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ee4d0-110">[in] Lunghezza del buffer di versione.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="ee4d0-111">[fuori] Puntatore alla lunghezza della stringa del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee4d0-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ee4d0-112">Return Value</span></span>  
 <span data-ttu-id="ee4d0-113">Questo metodo restituisce i codici di errore COM (Component Object Model) standard, come definito in WinError.h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="ee4d0-114">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="ee4d0-114">Return code</span></span>|<span data-ttu-id="ee4d0-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee4d0-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ee4d0-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee4d0-116">S_OK</span></span>|<span data-ttu-id="ee4d0-117">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="ee4d0-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ee4d0-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ee4d0-119">Il buffer di versione non è sufficientemente grande per archiviare la stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="ee4d0-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ee4d0-120">E_POINTER</span></span>|<span data-ttu-id="ee4d0-121">`pdwLength` è null.</span><span class="sxs-lookup"><span data-stu-id="ee4d0-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee4d0-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee4d0-122">Requirements</span></span>  
 <span data-ttu-id="ee4d0-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee4d0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee4d0-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ee4d0-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee4d0-125">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="ee4d0-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee4d0-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee4d0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee4d0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee4d0-127">See also</span></span>

- [<span data-ttu-id="ee4d0-128">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="ee4d0-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="ee4d0-129">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="ee4d0-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="ee4d0-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="ee4d0-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
