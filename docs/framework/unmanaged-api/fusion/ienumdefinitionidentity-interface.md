---
title: Interfaccia IEnumDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
ms.openlocfilehash: 09c6431ec885c8b797dc9bb5f5c3ffe21890ccc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107949"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="e2f7b-102">Interfaccia IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="e2f7b-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="e2f7b-103">Funge da enumeratore per una raccolta di oggetti `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e2f7b-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f7b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2f7b-104">Syntax</span></span>  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e2f7b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e2f7b-105">Methods</span></span>  
  
|<span data-ttu-id="e2f7b-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="e2f7b-106">Method</span></span>|<span data-ttu-id="e2f7b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2f7b-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="e2f7b-108">Ottiene un puntatore a interfaccia a un nuovo oggetto `IEnumDefinitionIdentity` contenente gli stessi membri di questo `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e2f7b-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="e2f7b-109">Ottiene il numero specificato di oggetti `IDefinitionIdentity`, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="e2f7b-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="e2f7b-110">Sposta il puntatore all'istruzione all'inizio di questo `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e2f7b-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="e2f7b-111">Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="e2f7b-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2f7b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2f7b-112">Requirements</span></span>  
 <span data-ttu-id="e2f7b-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2f7b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2f7b-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="e2f7b-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e2f7b-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2f7b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f7b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2f7b-116">See also</span></span>

- [<span data-ttu-id="e2f7b-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="e2f7b-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e2f7b-118">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="e2f7b-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
