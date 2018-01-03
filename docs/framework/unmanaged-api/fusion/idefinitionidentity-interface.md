---
title: Interfaccia IDefinitionIdentity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionIdentity
helpviewer_keywords: IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b074ae2a0a4e4e65f0402ff35888b557b00dd071
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="f0d28-102">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="f0d28-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="f0d28-103">Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="f0d28-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0d28-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f0d28-104">Methods</span></span>  
  
|<span data-ttu-id="f0d28-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f0d28-105">Method</span></span>|<span data-ttu-id="f0d28-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0d28-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="f0d28-107">Ottiene un puntatore a interfaccia a un nuovo `IDefinitionIdentity` oggetto è uguale a `IDefinitionIdentity`, tranne le modifiche di attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="f0d28-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="f0d28-108">Ottiene un puntatore a interfaccia a un [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) oggetto che contiene gli attributi associati a questo `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f0d28-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="f0d28-109">Ottiene il valore dell'attributo con il nome specificato nello spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="f0d28-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="f0d28-110">Imposta l'attributo con il nome specificato nello spazio dei nomi specificato al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="f0d28-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0d28-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0d28-111">Requirements</span></span>  
 <span data-ttu-id="f0d28-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0d28-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0d28-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="f0d28-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f0d28-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0d28-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d28-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0d28-115">See Also</span></span>  
 [<span data-ttu-id="f0d28-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="f0d28-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
