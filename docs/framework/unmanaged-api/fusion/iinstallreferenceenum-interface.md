---
title: Interfaccia IInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d29b9e2a9b9022f682065816a62734d6c5b2d62
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796412"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="baba8-102">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="baba8-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="baba8-103">Rappresenta un enumeratore per gli assembly di riferimento installati nell'Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="baba8-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baba8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="baba8-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="baba8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="baba8-105">Methods</span></span>  
  
|<span data-ttu-id="baba8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="baba8-106">Method</span></span>|<span data-ttu-id="baba8-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="baba8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="baba8-108">Metodo GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="baba8-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="baba8-109">Ottiene un puntatore al successivo `IInstallReferenceItem` contenuto `IInstallReferenceEnum`nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="baba8-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="baba8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="baba8-110">Requirements</span></span>  
 <span data-ttu-id="baba8-111">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baba8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baba8-112">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="baba8-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="baba8-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baba8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baba8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baba8-114">See also</span></span>

- [<span data-ttu-id="baba8-115">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="baba8-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="baba8-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="baba8-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
