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
ms.openlocfilehash: 2aed89008dd2fa86b38f243c8e7cca1bdda901e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497774"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="2ef8a-102">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="2ef8a-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="2ef8a-103">Rappresenta un enumeratore per gli assembly di riferimento installato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ef8a-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2ef8a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="2ef8a-105">Methods</span></span>  
  
|<span data-ttu-id="2ef8a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="2ef8a-106">Method</span></span>|<span data-ttu-id="2ef8a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ef8a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ef8a-108">Metodo GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="2ef8a-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="2ef8a-109">Ottiene un puntatore al successivo `IInstallReferenceItem` contenuti in questo `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ef8a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ef8a-110">Requirements</span></span>  
 <span data-ttu-id="2ef8a-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ef8a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ef8a-112">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2ef8a-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2ef8a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ef8a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef8a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ef8a-114">See also</span></span>
- [<span data-ttu-id="2ef8a-115">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="2ef8a-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="2ef8a-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="2ef8a-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
