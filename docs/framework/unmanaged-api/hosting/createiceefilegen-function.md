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
ms.openlocfilehash: 294b82efd66704014aab1b73171afe9165f17664
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616450"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="94156-102">Funzione CreateICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="94156-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="94156-103">Crea un oggetto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="94156-103">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="94156-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="94156-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94156-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94156-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94156-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="94156-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="94156-107">out Puntatore all'indirizzo di un nuovo `ICeeFileGen` oggetto.</span><span class="sxs-lookup"><span data-stu-id="94156-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94156-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="94156-108">Return Value</span></span>  
 <span data-ttu-id="94156-109">Questo metodo restituisce i codici di errore COM standard.</span><span class="sxs-lookup"><span data-stu-id="94156-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94156-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="94156-110">Remarks</span></span>  
 <span data-ttu-id="94156-111">L' `ICeeFileGen` oggetto viene utilizzato per creare file eseguibili di tipo PE (Portable Executable) Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="94156-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="94156-112">Chiamare la funzione [DestroyICeeFileGen](destroyiceefilegen-function.md) per eliminare definitivamente l'oggetto al termine dell'operazione `ICeeFileGen` .</span><span class="sxs-lookup"><span data-stu-id="94156-112">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94156-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94156-113">Requirements</span></span>  
 <span data-ttu-id="94156-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94156-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94156-115">**Intestazione:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="94156-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="94156-116">**Libreria:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="94156-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="94156-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94156-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94156-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94156-118">See also</span></span>

- [<span data-ttu-id="94156-119">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="94156-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
