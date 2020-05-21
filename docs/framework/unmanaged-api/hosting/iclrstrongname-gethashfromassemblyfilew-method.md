---
title: Metodo ICLRStrongName::GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: f44753b3e836b43bc09548a35eb68f0f22e3170f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762136"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="de151-102">Metodo ICLRStrongName::GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="de151-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="de151-103">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="de151-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de151-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de151-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de151-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="de151-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="de151-106">in Percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="de151-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="de151-107">Questo parametro deve essere una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="de151-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="de151-108">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="de151-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="de151-109">Usare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="de151-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="de151-110">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="de151-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="de151-111">in Dimensione massima richiesta di `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="de151-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="de151-112">out Dimensione restituita, in byte, di `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="de151-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de151-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="de151-113">Return Value</span></span>  
 <span data-ttu-id="de151-114">`S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="de151-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de151-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de151-115">Requirements</span></span>  
 <span data-ttu-id="de151-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de151-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de151-117">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="de151-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="de151-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="de151-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de151-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de151-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de151-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de151-120">See also</span></span>

- [<span data-ttu-id="de151-121">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="de151-121">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="de151-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="de151-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
