---
title: Funzione CreateICeeFileGen
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: de27851b4afc3eccad46531848c68723bff346d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136827"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="b8b91-102">Funzione CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="b8b91-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="b8b91-103">Crea un oggetto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="b8b91-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="b8b91-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b8b91-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8b91-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8b91-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8b91-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8b91-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="b8b91-107">out Puntatore all'indirizzo di un nuovo oggetto `ICeeFileGen`.</span><span class="sxs-lookup"><span data-stu-id="b8b91-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8b91-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b8b91-108">Return Value</span></span>  
 <span data-ttu-id="b8b91-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="b8b91-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8b91-110">Note</span><span class="sxs-lookup"><span data-stu-id="b8b91-110">Remarks</span></span>  
 <span data-ttu-id="b8b91-111">L'oggetto `ICeeFileGen` viene utilizzato per creare file eseguibili di tipo PE (Portable Executable) Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b8b91-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="b8b91-112">Chiamare la funzione [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) per eliminare definitivamente l'oggetto `ICeeFileGen` al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="b8b91-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8b91-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8b91-113">Requirements</span></span>  
 <span data-ttu-id="b8b91-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8b91-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8b91-115">**Intestazione:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="b8b91-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="b8b91-116">**Libreria:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="b8b91-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="b8b91-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8b91-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b91-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8b91-118">See also</span></span>

- [<span data-ttu-id="b8b91-119">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="b8b91-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
