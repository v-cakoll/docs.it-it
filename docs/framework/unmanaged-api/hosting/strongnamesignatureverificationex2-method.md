---
title: Metodo StrongNameSignatureVerificationEx2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d2ac3788b68626eb04a6f2cbac995b8e5b4ebf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442582"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="03159-102">Metodo StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="03159-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="03159-103">Verifica la firma di un assembly con nome sicuro e fornisce il mapping tra la chiave ECMA a una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="03159-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03159-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03159-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03159-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03159-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="03159-106">[in] Il percorso del file di (.exe o DLL) eseguibile portabile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="03159-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="03159-107">[in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="03159-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="03159-108">[in] Un puntatore per il mapping dalla chiave pubblica ECMA per il tasto effettivo utilizzato per la verifica.</span><span class="sxs-lookup"><span data-stu-id="03159-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="03159-109">[in] La lunghezza della chiave pubblica ECMA reale.</span><span class="sxs-lookup"><span data-stu-id="03159-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="03159-110">[out] `true` se la firma nome sicuro è stato verificato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="03159-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="03159-111">Questo parametro viene impostato anche su `false` se la verifica ha esito positivo a causa delle impostazioni del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="03159-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03159-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="03159-112">Return Value</span></span>  
 <span data-ttu-id="03159-113">`S_OK` Se la verifica ha avuto esito positivo. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="03159-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03159-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03159-114">Requirements</span></span>  
 <span data-ttu-id="03159-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03159-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03159-116">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="03159-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="03159-117">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="03159-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03159-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03159-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03159-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03159-119">See Also</span></span>  
 [<span data-ttu-id="03159-120">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="03159-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="03159-121">Metodo StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="03159-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="03159-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="03159-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
