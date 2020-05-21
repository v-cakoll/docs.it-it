---
title: Metodo ICLRStrongName::GetHashFromHandle
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
ms.openlocfilehash: e2d71f7c61b02273bdcaf182f6f79ca3c2a2c75f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762081"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="e279f-102">Metodo ICLRStrongName::GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="e279f-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="e279f-103">Genera un hash sul contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="e279f-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e279f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e279f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e279f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e279f-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="e279f-106">in Handle del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="e279f-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="e279f-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="e279f-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="e279f-108">Usare zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="e279f-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="e279f-109">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="e279f-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="e279f-110">in Dimensione massima richiesta di `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="e279f-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="e279f-111">out Dimensione, in byte, dell'oggetto restituito `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="e279f-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e279f-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e279f-112">Return Value</span></span>  
 <span data-ttu-id="e279f-113">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="e279f-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e279f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e279f-114">Requirements</span></span>  
 <span data-ttu-id="e279f-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e279f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e279f-116">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e279f-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e279f-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e279f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e279f-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e279f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e279f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e279f-119">See also</span></span>

- [<span data-ttu-id="e279f-120">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e279f-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
