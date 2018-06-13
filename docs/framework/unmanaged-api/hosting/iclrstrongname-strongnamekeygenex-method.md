---
title: Metodo ICLRStrongName::StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b213285b3c533488cfa48198951275925c0e37ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436186"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="3a511-102">Metodo ICLRStrongName::StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="3a511-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="3a511-103">Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata, per l'utilizzo con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="3a511-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a511-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a511-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a511-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3a511-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="3a511-106">[in] Il nome di contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="3a511-106">[in] The requested key container name.</span></span> <span data-ttu-id="3a511-107">`wszKeyContainer` deve essere una stringa non vuota o null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="3a511-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3a511-108">[in] Un valore che specifica se mantenere la chiave è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="3a511-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="3a511-109">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3a511-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="3a511-110">0x00000000 - utilizzato quando `wszKeyContainer` è null per generare un nome di contenitore di chiavi temporaneo.</span><span class="sxs-lookup"><span data-stu-id="3a511-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="3a511-111">0x00000001 (`SN_LEAVE_KEY`)-specifica che la chiave deve essere registrata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="3a511-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="3a511-112">[in] La dimensione richiesta della chiave in bit.</span><span class="sxs-lookup"><span data-stu-id="3a511-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="3a511-113">[out] La coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="3a511-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="3a511-114">[out] Le dimensioni, in byte, di `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="3a511-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a511-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3a511-115">Return Value</span></span>  
 <span data-ttu-id="3a511-116">`S_OK` Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="3a511-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a511-117">Note</span><span class="sxs-lookup"><span data-stu-id="3a511-117">Remarks</span></span>  
 <span data-ttu-id="3a511-118">Le versioni di .NET Framework 1.0 e 1.1 richiedono un `dwKeySize` pari a 1024 bit per firmare un assembly con un nome sicuro; versione 2.0 include il supporto per le chiavi a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="3a511-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="3a511-119">Dopo il recupero della chiave, è necessario chiamare il [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="3a511-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a511-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a511-120">Requirements</span></span>  
 <span data-ttu-id="3a511-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a511-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a511-122">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="3a511-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3a511-123">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3a511-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a511-124">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a511-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a511-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a511-125">See Also</span></span>  
 [<span data-ttu-id="3a511-126">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="3a511-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="3a511-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3a511-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
