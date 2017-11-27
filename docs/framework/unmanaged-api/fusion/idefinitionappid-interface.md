---
title: Interfaccia IDefinitionAppId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionAppId
helpviewer_keywords: IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 382c82ff773d0ab1c046fc131fa87a4f74d19ea6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="329d5-102">Interfaccia IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="329d5-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="329d5-103">Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="329d5-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="329d5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="329d5-104">Methods</span></span>  
  
|<span data-ttu-id="329d5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="329d5-105">Method</span></span>|<span data-ttu-id="329d5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329d5-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="329d5-107">Ottiene una stringa formattata che rappresenta il codice in questo `IDefinitionAppId` oggetto.</span><span class="sxs-lookup"><span data-stu-id="329d5-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="329d5-108">Imposta il codice di questo `IDefinitionAppId` valore di stringa formattato dell'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="329d5-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="329d5-109">Ottiene un puntatore a interfaccia a un [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) oggetto che contiene gli assembly nel percorso dell'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="329d5-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="329d5-110">Imposta il percorso dell'applicazione per l'assembly nell'ambito corrente sul valore specificato fa riferimento [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="329d5-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="329d5-111">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di token per una sottoscrizione a questo `IDefinitionAppId` oggetto.</span><span class="sxs-lookup"><span data-stu-id="329d5-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="329d5-112">Imposta l'identificatore del token per una sottoscrizione a questo `IDefinitionAppId` oggetto con il valore di stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="329d5-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="329d5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="329d5-113">Requirements</span></span>  
 <span data-ttu-id="329d5-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="329d5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="329d5-115">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="329d5-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="329d5-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="329d5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329d5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="329d5-117">See Also</span></span>  
 [<span data-ttu-id="329d5-118">Fusion (interfacce)</span><span class="sxs-lookup"><span data-stu-id="329d5-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
