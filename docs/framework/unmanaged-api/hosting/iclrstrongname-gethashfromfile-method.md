---
title: Metodo ICLRStrongName::GetHashFromFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18a619bf2a98b2140ab126745305a85f4e1fd05c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484288"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="df494-102">Metodo ICLRStrongName::GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="df494-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="df494-103">Genera un hash basato sul contenuto del file specificato.</span><span class="sxs-lookup"><span data-stu-id="df494-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df494-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df494-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df494-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="df494-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="df494-106">[in] Il nome del file da hash.</span><span class="sxs-lookup"><span data-stu-id="df494-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="df494-107">[in, out] L'algoritmo da utilizzare durante la generazione di hash.</span><span class="sxs-lookup"><span data-stu-id="df494-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="df494-108">Gli algoritmi validi sono quelli definiti per la funzione CryptoAPI Win32.</span><span class="sxs-lookup"><span data-stu-id="df494-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="df494-109">Se `piHashAlg` è impostato su 0, l'algoritmo predefinito viene utilizzato CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="df494-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="df494-110">[out] Matrice di byte contenente il valore hash generato.</span><span class="sxs-lookup"><span data-stu-id="df494-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="df494-111">[in] Le dimensioni massime del buffer che `pbHash` punta a.</span><span class="sxs-lookup"><span data-stu-id="df494-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="df494-112">[out] Le dimensioni, in byte, del valore restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="df494-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df494-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="df494-113">Return Value</span></span>  
 <span data-ttu-id="df494-114">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="df494-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df494-115">Note</span><span class="sxs-lookup"><span data-stu-id="df494-115">Remarks</span></span>  
 <span data-ttu-id="df494-116">Questo metodo è quello utilizzato per il [GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) metodo, ad eccezione del fatto che il nome del file specifica è ANSI invece di Unicode.</span><span class="sxs-lookup"><span data-stu-id="df494-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df494-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df494-117">Requirements</span></span>  
 <span data-ttu-id="df494-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df494-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df494-119">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="df494-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="df494-120">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="df494-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df494-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df494-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df494-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df494-122">See also</span></span>
- [<span data-ttu-id="df494-123">Metodo GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="df494-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="df494-124">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="df494-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
