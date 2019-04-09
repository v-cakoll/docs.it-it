---
title: Interfaccia IReferenceIdentity
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd46ea26532074c9ea42da4d07a38ed583aad076
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220162"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="5b9e1-102">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="5b9e1-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="5b9e1-103">Rappresenta un riferimento a una firma univoca di un oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="5b9e1-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b9e1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5b9e1-104">Methods</span></span>  
  
|<span data-ttu-id="5b9e1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5b9e1-105">Method</span></span>|<span data-ttu-id="5b9e1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b9e1-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="5b9e1-107">Ottiene un puntatore a interfaccia a una nuova `IReferenceIdentity` identica a questa istanza `IReferenceIdentity`, fatta eccezione per le modifiche di attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="5b9e1-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="5b9e1-108">Ottiene un puntatore a interfaccia a un `IEnumIDENTITY_ATTRIBUTE` istanza che contiene gli attributi associati a questo `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="5b9e1-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="5b9e1-109">Ottiene il valore dell'attributo nello spazio dei nomi specificato, con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="5b9e1-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="5b9e1-110">Imposta l'attributo con lo spazio dei nomi specificato e il nome specificato al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="5b9e1-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b9e1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b9e1-111">Requirements</span></span>  
 <span data-ttu-id="5b9e1-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b9e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b9e1-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="5b9e1-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="5b9e1-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5b9e1-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b9e1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b9e1-115">See also</span></span>

- [<span data-ttu-id="5b9e1-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="5b9e1-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="5b9e1-117">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="5b9e1-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
