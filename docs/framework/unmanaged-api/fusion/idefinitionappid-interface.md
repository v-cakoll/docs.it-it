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
ms.openlocfilehash: 929909a7f2c4fa1799c8fed94787b8f853c7eac2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796511"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="af827-102">Interfaccia IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="af827-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="af827-103">Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="af827-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af827-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="af827-104">Methods</span></span>  
  
|<span data-ttu-id="af827-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="af827-105">Method</span></span>|<span data-ttu-id="af827-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af827-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="af827-107">Ottiene una stringa formattata che rappresenta il codice in `IDefinitionAppId` questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="af827-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="af827-108">Imposta il codice di questo `IDefinitionAppId` oggetto sul valore stringa formattato specificato.</span><span class="sxs-lookup"><span data-stu-id="af827-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="af827-109">Ottiene un puntatore a interfaccia a un oggetto [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) che contiene gli assembly nel percorso dell'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="af827-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="af827-110">Imposta il percorso dell'applicazione per l'assembly nell'ambito corrente sul valore a cui fa riferimento l'oggetto [IDefinitionIdentity](idefinitionidentity-interface.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="af827-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="af827-111">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione di `IDefinitionAppId` questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="af827-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="af827-112">Imposta l'identificatore del token per una sottoscrizione di `IDefinitionAppId` questo oggetto sul valore stringa specificato.</span><span class="sxs-lookup"><span data-stu-id="af827-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af827-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af827-113">Requirements</span></span>  
 <span data-ttu-id="af827-114">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af827-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af827-115">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="af827-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="af827-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af827-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af827-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af827-117">See also</span></span>

- [<span data-ttu-id="af827-118">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="af827-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
