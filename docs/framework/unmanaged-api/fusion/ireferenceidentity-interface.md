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
ms.openlocfilehash: 8f6a117d1e2fe76c271b0b014e6079370c8b4fe4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127071"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="01c85-102">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="01c85-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="01c85-103">Rappresenta un riferimento alla firma univoca di un oggetto di codice.</span><span class="sxs-lookup"><span data-stu-id="01c85-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01c85-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="01c85-104">Methods</span></span>  
  
|<span data-ttu-id="01c85-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="01c85-105">Method</span></span>|<span data-ttu-id="01c85-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01c85-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="01c85-107">Ottiene un puntatore a interfaccia a una nuova istanza di `IReferenceIdentity` identica a questa `IReferenceIdentity`, ad eccezione delle modifiche di attributo specificate.</span><span class="sxs-lookup"><span data-stu-id="01c85-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="01c85-108">Ottiene un puntatore a interfaccia a un'istanza di `IEnumIDENTITY_ATTRIBUTE` contenente gli attributi associati a questo `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="01c85-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="01c85-109">Ottiene il valore dell'attributo nello spazio dei nomi specificato, con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="01c85-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="01c85-110">Imposta l'attributo con lo spazio dei nomi specificato e il nome specificato sul valore specificato.</span><span class="sxs-lookup"><span data-stu-id="01c85-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01c85-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01c85-111">Requirements</span></span>  
 <span data-ttu-id="01c85-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01c85-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01c85-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="01c85-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="01c85-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01c85-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c85-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01c85-115">See also</span></span>

- [<span data-ttu-id="01c85-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="01c85-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="01c85-117">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="01c85-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
