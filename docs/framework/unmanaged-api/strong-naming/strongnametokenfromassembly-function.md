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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71058a1ff82335b2a341904805d06738e662c296
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798867"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="58d8d-102">Funzione StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="58d8d-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="58d8d-103">Crea un token con nome sicuro dal file di assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="58d8d-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="58d8d-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="58d8d-104">This function has been deprecated.</span></span> <span data-ttu-id="58d8d-105">Usare invece il metodo [ICLRStrongName:: StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="58d8d-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d8d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58d8d-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58d8d-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="58d8d-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="58d8d-108">in Percorso del file eseguibile di tipo PE per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="58d8d-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="58d8d-109">out Token del nome sicuro restituito.</span><span class="sxs-lookup"><span data-stu-id="58d8d-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="58d8d-110">out Dimensione, in byte, del token del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="58d8d-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58d8d-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="58d8d-111">Return Value</span></span>  
 <span data-ttu-id="58d8d-112">`true`al completamento; in caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="58d8d-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58d8d-113">Note</span><span class="sxs-lookup"><span data-stu-id="58d8d-113">Remarks</span></span>  
 <span data-ttu-id="58d8d-114">Un token di nome sicuro è il formato abbreviato di una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="58d8d-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="58d8d-115">Il token è un hash a 64 bit creato dalla chiave pubblica usata per firmare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="58d8d-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="58d8d-116">Il token fa parte del nome sicuro dell'assembly e può essere letto dai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="58d8d-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="58d8d-117">Dopo la creazione del token, è necessario chiamare la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) per rilasciare la memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="58d8d-117">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="58d8d-118">Se la `StrongNameTokenFromAssembly` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.</span><span class="sxs-lookup"><span data-stu-id="58d8d-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58d8d-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58d8d-119">Requirements</span></span>  
 <span data-ttu-id="58d8d-120">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58d8d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d8d-121">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="58d8d-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="58d8d-122">**Libreria** Incluso come risorsa in mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="58d8d-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="58d8d-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d8d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d8d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58d8d-124">See also</span></span>

- [<span data-ttu-id="58d8d-125">Metodo StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="58d8d-125">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="58d8d-126">Metodo StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="58d8d-126">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="58d8d-127">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="58d8d-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
