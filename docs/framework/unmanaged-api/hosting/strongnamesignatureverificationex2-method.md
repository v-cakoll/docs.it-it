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
ms.openlocfilehash: cf8d6b7e45c0012d223173c85a92fac4fb044c6c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141405"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="37e45-102">Metodo StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="37e45-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="37e45-103">Verifica la firma di un assembly con nome sicuro e fornisce un mapping dalla chiave ECMA a una chiave reale.</span><span class="sxs-lookup"><span data-stu-id="37e45-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37e45-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37e45-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37e45-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="37e45-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="37e45-106">in Percorso del file eseguibile (exe o dll) portatile per l'assembly da verificare.</span><span class="sxs-lookup"><span data-stu-id="37e45-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="37e45-107">[in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del registro di sistema; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="37e45-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="37e45-108">in Puntatore al mapping dalla chiave pubblica ECMA alla chiave reale utilizzata per la verifica.</span><span class="sxs-lookup"><span data-stu-id="37e45-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="37e45-109">in Lunghezza della chiave pubblica ECMA reale.</span><span class="sxs-lookup"><span data-stu-id="37e45-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="37e45-110">[out] `true` se la firma del nome sicuro è stata verificata. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="37e45-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="37e45-111">Questo parametro viene impostato anche su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="37e45-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37e45-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="37e45-112">Return Value</span></span>  
 <span data-ttu-id="37e45-113">`S_OK` se la verifica ha avuto esito positivo; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="37e45-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37e45-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37e45-114">Requirements</span></span>  
 <span data-ttu-id="37e45-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37e45-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37e45-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="37e45-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="37e45-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="37e45-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37e45-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37e45-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37e45-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37e45-119">See also</span></span>

- [<span data-ttu-id="37e45-120">Metodo StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="37e45-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="37e45-121">Metodo StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="37e45-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="37e45-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="37e45-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
