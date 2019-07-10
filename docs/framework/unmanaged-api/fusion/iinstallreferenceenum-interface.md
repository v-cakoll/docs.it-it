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
ms.openlocfilehash: 5781254b508887f2e76f6ca0eca6a2830ada172b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774010"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="80eaf-102">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="80eaf-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="80eaf-103">Rappresenta un enumeratore per gli assembly di riferimento installato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="80eaf-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80eaf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80eaf-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="80eaf-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="80eaf-105">Methods</span></span>  
  
|<span data-ttu-id="80eaf-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="80eaf-106">Method</span></span>|<span data-ttu-id="80eaf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80eaf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80eaf-108">Metodo GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="80eaf-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="80eaf-109">Ottiene un puntatore al successivo `IInstallReferenceItem` contenuti in questo `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="80eaf-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80eaf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80eaf-110">Requirements</span></span>  
 <span data-ttu-id="80eaf-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80eaf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80eaf-112">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="80eaf-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="80eaf-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80eaf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80eaf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80eaf-114">See also</span></span>

- [<span data-ttu-id="80eaf-115">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="80eaf-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="80eaf-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="80eaf-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
