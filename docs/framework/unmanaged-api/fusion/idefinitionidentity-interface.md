---
title: Interfaccia IDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697537"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="a7e24-102">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="a7e24-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="a7e24-103">Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="a7e24-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7e24-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a7e24-104">Methods</span></span>  
  
|<span data-ttu-id="a7e24-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a7e24-105">Method</span></span>|<span data-ttu-id="a7e24-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7e24-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="a7e24-107">Ottiene un puntatore a interfaccia a una nuova `IDefinitionIdentity` che è identico a questo oggetto `IDefinitionIdentity`, fatta eccezione per le modifiche di attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="a7e24-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="a7e24-108">Ottiene un puntatore a interfaccia a un [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) che contiene gli attributi associati a questo oggetto `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="a7e24-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="a7e24-109">Ottiene il valore dell'attributo con il nome specificato nello spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="a7e24-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="a7e24-110">Imposta l'attributo con il nome specificato nello spazio dei nomi specificato al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="a7e24-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7e24-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7e24-111">Requirements</span></span>  
 <span data-ttu-id="a7e24-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7e24-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e24-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="a7e24-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a7e24-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7e24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e24-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7e24-115">See also</span></span>

- [<span data-ttu-id="a7e24-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="a7e24-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
