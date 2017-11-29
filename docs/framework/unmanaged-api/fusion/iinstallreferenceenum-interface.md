---
title: Interfaccia IInstallReferenceEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceEnum
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceEnum
helpviewer_keywords: IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3847d06c77a92eb6e63542f03405ca0cb9c9560
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="b1b2f-102">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="b1b2f-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="b1b2f-103">Rappresenta un enumeratore per gli assembly di riferimento installati nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="b1b2f-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b2f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1b2f-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b1b2f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b1b2f-105">Methods</span></span>  
  
|<span data-ttu-id="b1b2f-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b1b2f-106">Method</span></span>|<span data-ttu-id="b1b2f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1b2f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1b2f-108">GetNextInstallReferenceItem (metodo)</span><span class="sxs-lookup"><span data-stu-id="b1b2f-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="b1b2f-109">Ottiene un puntatore al successivo `IInstallReferenceItem` contenuti in questo `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="b1b2f-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1b2f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1b2f-110">Requirements</span></span>  
 <span data-ttu-id="b1b2f-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1b2f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b2f-112">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b1b2f-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b1b2f-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1b2f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b2f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1b2f-114">See Also</span></span>  
 [<span data-ttu-id="b1b2f-115">Fusion (interfacce)</span><span class="sxs-lookup"><span data-stu-id="b1b2f-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="b1b2f-116">IInstallReferenceItem (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b1b2f-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
