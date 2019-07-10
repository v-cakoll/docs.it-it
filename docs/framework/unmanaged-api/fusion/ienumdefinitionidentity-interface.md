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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bbd8476b7778de6d0023f3a8522a44be6626884
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751522"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="b99b7-102">Interfaccia IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="b99b7-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="b99b7-103">Serve come enumeratore per una raccolta di `IDefinitionIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="b99b7-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b99b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b99b7-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="b99b7-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b99b7-105">Methods</span></span>  
  
|<span data-ttu-id="b99b7-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b99b7-106">Method</span></span>|<span data-ttu-id="b99b7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b99b7-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="b99b7-108">Ottiene un puntatore a interfaccia a una nuova `IEnumDefinitionIdentity` oggetto che contiene gli stessi membri di questo `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b99b7-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="b99b7-109">Ottiene il numero specificato di `IDefinitionIdentity` oggetti, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="b99b7-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="b99b7-110">Sposta il puntatore all'istruzione all'inizio di questo `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b99b7-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="b99b7-111">Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="b99b7-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b99b7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b99b7-112">Requirements</span></span>  
 <span data-ttu-id="b99b7-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b99b7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b99b7-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="b99b7-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b99b7-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b99b7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b99b7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b99b7-116">See also</span></span>

- [<span data-ttu-id="b99b7-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="b99b7-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="b99b7-118">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="b99b7-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
