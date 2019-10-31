---
title: Funzione GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: 866b34acae333f043d8e13f4d0ebd55f32046334
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140722"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="9a812-102">Funzione GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="9a812-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="9a812-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="9a812-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="9a812-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="9a812-104">This function has been deprecated.</span></span> <span data-ttu-id="9a812-105">Usare invece il metodo [ICLRStrongName:: GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9a812-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a812-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a812-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a812-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a812-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="9a812-108">in Percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="9a812-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9a812-109">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="9a812-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="9a812-110">Usare zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="9a812-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9a812-111">out Buffer hash restituito.</span><span class="sxs-lookup"><span data-stu-id="9a812-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9a812-112">in Dimensioni massime richieste di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="9a812-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9a812-113">out Dimensioni restituite, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="9a812-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a812-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a812-114">Requirements</span></span>  
 <span data-ttu-id="9a812-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a812-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a812-116">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="9a812-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9a812-117">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9a812-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a812-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a812-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a812-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a812-119">See also</span></span>

- [<span data-ttu-id="9a812-120">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="9a812-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="9a812-121">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="9a812-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="9a812-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9a812-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
