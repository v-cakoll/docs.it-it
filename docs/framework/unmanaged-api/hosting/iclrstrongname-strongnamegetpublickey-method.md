---
title: Metodo ICLRStrongName::StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: 5a20bde64830617090c92afe5fae3a603cf9103b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763130"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="90348-102">Metodo ICLRStrongName::StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="90348-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="90348-103">Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="90348-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="90348-104">È possibile specificare la coppia di chiavi come nome del contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come raccolta di byte non elaborata.</span><span class="sxs-lookup"><span data-stu-id="90348-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90348-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90348-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90348-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="90348-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="90348-107">in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="90348-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="90348-108">Se `pbKeyBlob` è null, è `szKeyContainer` necessario specificare un contenitore valido all'interno del CSP.</span><span class="sxs-lookup"><span data-stu-id="90348-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="90348-109">In questo caso, il metodo [ICLRStrongName:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="90348-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="90348-110">Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.</span><span class="sxs-lookup"><span data-stu-id="90348-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="90348-111">Le chiavi devono essere chiavi di firma Rivest-Shamir-Adleman (RSA) a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="90348-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="90348-112">Al momento non sono supportati altri tipi di chiavi.</span><span class="sxs-lookup"><span data-stu-id="90348-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="90348-113">in Puntatore alla coppia di chiavi pubblica/privata.</span><span class="sxs-lookup"><span data-stu-id="90348-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="90348-114">Questa coppia è nel formato creato dalla `CryptExportKey` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="90348-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="90348-115">Se `pbKeyBlob` è null, si presuppone che il contenitore di chiavi specificato da `szKeyContainer` contenga la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="90348-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="90348-116">in Dimensione, in byte, di `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="90348-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="90348-117">out BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="90348-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="90348-118">Il `ppbPublicKeyBlob` parametro viene allocato dal Common Language Runtime e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="90348-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="90348-119">Il chiamante deve liberare la memoria tramite il metodo [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="90348-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="90348-120">out Dimensioni del BLOB della chiave pubblica restituito.</span><span class="sxs-lookup"><span data-stu-id="90348-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90348-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="90348-121">Return Value</span></span>  
 <span data-ttu-id="90348-122">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="90348-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90348-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="90348-123">Remarks</span></span>  
 <span data-ttu-id="90348-124">La chiave pubblica è contenuta in una struttura [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="90348-124">The public key is contained in a [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90348-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90348-125">Requirements</span></span>  
 <span data-ttu-id="90348-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90348-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90348-127">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="90348-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="90348-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="90348-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90348-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90348-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90348-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90348-130">See also</span></span>

- [<span data-ttu-id="90348-131">Metodo StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="90348-131">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="90348-132">Struttura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="90348-132">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="90348-133">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="90348-133">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
