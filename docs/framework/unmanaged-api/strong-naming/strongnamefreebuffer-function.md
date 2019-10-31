---
title: Funzione StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: 11821acbeeb04ae09464eb0e032b9bf387914168
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095058"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="fab04-102">Funzione StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="fab04-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="fab04-103">Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="fab04-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="fab04-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="fab04-104">This function has been deprecated.</span></span> <span data-ttu-id="fab04-105">Usare invece il metodo [ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fab04-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fab04-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fab04-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fab04-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="fab04-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="fab04-108">in Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="fab04-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fab04-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fab04-109">Requirements</span></span>  
 <span data-ttu-id="fab04-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fab04-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fab04-111">**Intestazione:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="fab04-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fab04-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fab04-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fab04-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fab04-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab04-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fab04-114">See also</span></span>

- [<span data-ttu-id="fab04-115">Metodo StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="fab04-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="fab04-116">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="fab04-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
