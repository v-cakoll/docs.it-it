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
ms.openlocfilehash: f97e6f16029b9a273a68d52b830939819bfa5380
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083557"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="c46ec-102">Metodo ICLRStrongName::StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="c46ec-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="c46ec-103">Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata per l'uso di nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="c46ec-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c46ec-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c46ec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c46ec-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c46ec-106">[in] Il nome di contenitore di chiavi richiesto.</span><span class="sxs-lookup"><span data-stu-id="c46ec-106">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="c46ec-107">deve essere una stringa non vuota o null per generare un nome temporaneo.</span><span class="sxs-lookup"><span data-stu-id="c46ec-107">must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c46ec-108">[in] Un valore che specifica se lasciare la chiave di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c46ec-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="c46ec-109">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c46ec-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="c46ec-110">0x00000000 - utilizzato quando `wszKeyContainer` è null per generare un nome di contenitore di chiavi temporanee.</span><span class="sxs-lookup"><span data-stu-id="c46ec-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="c46ec-111">0x00000001 (`SN_LEAVE_KEY`): Specifica che la chiave deve essere registrata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="c46ec-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="c46ec-112">[in] Dimensione richiesta della chiave, espressa in bit.</span><span class="sxs-lookup"><span data-stu-id="c46ec-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="c46ec-113">[out] La coppia di chiavi pubblica/privata restituita.</span><span class="sxs-lookup"><span data-stu-id="c46ec-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="c46ec-114">[out] Le dimensioni, in byte, di `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="c46ec-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c46ec-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c46ec-115">Return Value</span></span>  
 `S_OK` <span data-ttu-id="c46ec-116">Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="c46ec-116">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c46ec-117">Note</span><span class="sxs-lookup"><span data-stu-id="c46ec-117">Remarks</span></span>  
 <span data-ttu-id="c46ec-118">Le versioni di .NET Framework 1.0 e 1.1 richiedono un `dwKeySize` pari a 1024 bit per firmare un assembly con nome sicuro; versione 2.0 aggiunge il supporto per le chiavi a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="c46ec-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="c46ec-119">Una volta recuperata la chiave, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="c46ec-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c46ec-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c46ec-120">Requirements</span></span>  
 <span data-ttu-id="c46ec-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c46ec-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c46ec-122">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c46ec-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c46ec-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c46ec-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c46ec-124">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c46ec-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c46ec-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c46ec-125">See also</span></span>

- [<span data-ttu-id="c46ec-126">Metodo StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="c46ec-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="c46ec-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c46ec-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
