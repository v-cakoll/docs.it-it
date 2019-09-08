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
ms.openlocfilehash: 84c595bfdcca84ee43a53e2ea913cc978ae0953e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796533"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="8b416-102">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="8b416-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="8b416-103">Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="8b416-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b416-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8b416-104">Methods</span></span>  
  
|<span data-ttu-id="8b416-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8b416-105">Method</span></span>|<span data-ttu-id="8b416-106">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8b416-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="8b416-107">Ottiene un puntatore a interfaccia a un `IDefinitionIdentity` nuovo oggetto identico `IDefinitionIdentity`a, ad eccezione delle modifiche di attributo specificate.</span><span class="sxs-lookup"><span data-stu-id="8b416-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="8b416-108">Ottiene un puntatore a interfaccia a un oggetto [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) che contiene gli attributi associati `IDefinitionIdentity`all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8b416-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="8b416-109">Ottiene il valore dell'attributo con il nome specificato nello spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="8b416-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="8b416-110">Imposta l'attributo con il nome specificato nello spazio dei nomi specificato sul valore specificato.</span><span class="sxs-lookup"><span data-stu-id="8b416-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b416-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b416-111">Requirements</span></span>  
 <span data-ttu-id="8b416-112">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b416-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b416-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="8b416-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="8b416-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b416-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b416-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b416-115">See also</span></span>

- [<span data-ttu-id="8b416-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="8b416-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
