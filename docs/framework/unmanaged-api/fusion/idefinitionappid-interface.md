---
title: Interfaccia IDefinitionAppId
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2735355097a1f3f581b3a4bc74f08d8f2ebf3bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430380"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="c1da4-102">Interfaccia IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="c1da4-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="c1da4-103">Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1da4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c1da4-104">Methods</span></span>  
  
|<span data-ttu-id="c1da4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c1da4-105">Method</span></span>|<span data-ttu-id="c1da4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1da4-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="c1da4-107">Ottiene una stringa formattata che rappresenta il codice in questo `IDefinitionAppId` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="c1da4-108">Imposta il codice di questo `IDefinitionAppId` valore di stringa formattato dell'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="c1da4-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="c1da4-109">Ottiene un puntatore a interfaccia a un [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) oggetto che contiene gli assembly nel percorso dell'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="c1da4-110">Imposta il percorso dell'applicazione per l'assembly nell'ambito corrente sul valore specificato fa riferimento [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="c1da4-111">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di token per una sottoscrizione a questo `IDefinitionAppId` oggetto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="c1da4-112">Imposta l'identificatore del token per una sottoscrizione a questo `IDefinitionAppId` oggetto con il valore di stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="c1da4-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1da4-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1da4-113">Requirements</span></span>  
 <span data-ttu-id="c1da4-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1da4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1da4-115">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="c1da4-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c1da4-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1da4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1da4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1da4-117">See Also</span></span>  
 [<span data-ttu-id="c1da4-118">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="c1da4-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
