---
title: Interfaccia IReferenceIdentity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceIdentity
helpviewer_keywords: IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c9696687f292d7dcaa3d430c1e269f0fedb05e98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="75d34-102">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="75d34-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="75d34-103">Rappresenta un riferimento alla firma univoca di un oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="75d34-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75d34-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="75d34-104">Methods</span></span>  
  
|<span data-ttu-id="75d34-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="75d34-105">Method</span></span>|<span data-ttu-id="75d34-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75d34-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="75d34-107">Ottiene un puntatore a interfaccia a un nuovo `IReferenceIdentity` istanza è uguale a `IReferenceIdentity`, tranne le modifiche di attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="75d34-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="75d34-108">Ottiene un puntatore a interfaccia a un `IEnumIDENTITY_ATTRIBUTE` istanza che contiene gli attributi associati a questo `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="75d34-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="75d34-109">Ottiene il valore dell'attributo nello spazio dei nomi specificato con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="75d34-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="75d34-110">Imposta l'attributo con lo spazio dei nomi specificato e il nome specificato per il valore specificato.</span><span class="sxs-lookup"><span data-stu-id="75d34-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75d34-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75d34-111">Requirements</span></span>  
 <span data-ttu-id="75d34-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75d34-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75d34-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="75d34-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="75d34-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75d34-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d34-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75d34-115">See Also</span></span>  
 [<span data-ttu-id="75d34-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="75d34-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="75d34-117">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="75d34-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
