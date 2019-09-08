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
ms.openlocfilehash: 88c2513229b6a4183cadbdc78e505910e01e152c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796480"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="7e2a3-102">Interfaccia IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="7e2a3-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="7e2a3-103">Funge da enumeratore per una raccolta di `IDefinitionIdentity` oggetti.</span><span class="sxs-lookup"><span data-stu-id="7e2a3-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e2a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e2a3-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="7e2a3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7e2a3-105">Methods</span></span>  
  
|<span data-ttu-id="7e2a3-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7e2a3-106">Method</span></span>|<span data-ttu-id="7e2a3-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7e2a3-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="7e2a3-108">Ottiene un puntatore a interfaccia a un `IEnumDefinitionIdentity` nuovo oggetto che contiene gli stessi membri di `IEnumDefinitionIdentity`questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="7e2a3-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="7e2a3-109">Ottiene il numero specificato di `IDefinitionIdentity` oggetti, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="7e2a3-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="7e2a3-110">Sposta il puntatore all'istruzione all'inizio di questo `IEnumDefinitionIdentity`oggetto.</span><span class="sxs-lookup"><span data-stu-id="7e2a3-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="7e2a3-111">Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="7e2a3-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e2a3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e2a3-112">Requirements</span></span>  
 <span data-ttu-id="7e2a3-113">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e2a3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e2a3-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="7e2a3-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="7e2a3-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e2a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2a3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e2a3-116">See also</span></span>

- [<span data-ttu-id="7e2a3-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="7e2a3-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="7e2a3-118">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="7e2a3-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
