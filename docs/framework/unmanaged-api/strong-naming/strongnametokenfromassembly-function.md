---
title: Funzione StrongNameTokenFromAssembly
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
ms.openlocfilehash: 6b9eca3f2f0267870866874ea27dc65812795f41
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121127"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="1eb56-102">Funzione StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="1eb56-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="1eb56-103">Crea un token con nome sicuro dal file di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="1eb56-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="1eb56-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="1eb56-104">This function has been deprecated.</span></span> <span data-ttu-id="1eb56-105">Usare invece il metodo [ICLRStrongName:: StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1eb56-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb56-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1eb56-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eb56-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1eb56-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="1eb56-108">in Percorso del file eseguibile di tipo PE per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="1eb56-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="1eb56-109">out Token del nome sicuro restituito.</span><span class="sxs-lookup"><span data-stu-id="1eb56-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="1eb56-110">out Dimensione, in byte, del token del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="1eb56-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1eb56-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1eb56-111">Return Value</span></span>  
 <span data-ttu-id="1eb56-112">`true` al completamento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1eb56-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eb56-113">Note</span><span class="sxs-lookup"><span data-stu-id="1eb56-113">Remarks</span></span>  
 <span data-ttu-id="1eb56-114">Un token di nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="1eb56-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="1eb56-115">Il token è un hash a 64 bit creato dalla chiave pubblica usata per firmare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="1eb56-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="1eb56-116">Il token fa parte del nome sicuro dell'assembly e può essere letto dai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1eb56-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="1eb56-117">Dopo la creazione del token, è necessario chiamare la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="1eb56-117">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="1eb56-118">Se la funzione `StrongNameTokenFromAssembly` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="1eb56-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eb56-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1eb56-119">Requirements</span></span>  
 <span data-ttu-id="1eb56-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eb56-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eb56-121">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="1eb56-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1eb56-122">**Libreria:** Incluso come risorsa in mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1eb56-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="1eb56-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eb56-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb56-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1eb56-124">See also</span></span>

- [<span data-ttu-id="1eb56-125">Metodo StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="1eb56-125">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="1eb56-126">Metodo StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="1eb56-126">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="1eb56-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1eb56-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
