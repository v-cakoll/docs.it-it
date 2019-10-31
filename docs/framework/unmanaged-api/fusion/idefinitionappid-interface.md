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
ms.openlocfilehash: 5114f74e80da925c7a153b9e481c54067152eaec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108208"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="742c0-102">Interfaccia IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="742c0-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="742c0-103">Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="742c0-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="742c0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="742c0-104">Methods</span></span>  
  
|<span data-ttu-id="742c0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="742c0-105">Method</span></span>|<span data-ttu-id="742c0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="742c0-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="742c0-107">Ottiene una stringa formattata che rappresenta il codice in questo oggetto `IDefinitionAppId`.</span><span class="sxs-lookup"><span data-stu-id="742c0-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="742c0-108">Imposta il codice di questo oggetto `IDefinitionAppId` sul valore stringa formattato specificato.</span><span class="sxs-lookup"><span data-stu-id="742c0-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="742c0-109">Ottiene un puntatore a interfaccia a un oggetto [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) che contiene gli assembly nel percorso dell'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="742c0-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="742c0-110">Imposta il percorso dell'applicazione per l'assembly nell'ambito corrente sul valore a cui fa riferimento l'oggetto [IDefinitionIdentity](idefinitionidentity-interface.md) specificato.</span><span class="sxs-lookup"><span data-stu-id="742c0-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="742c0-111">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione a questo oggetto `IDefinitionAppId`.</span><span class="sxs-lookup"><span data-stu-id="742c0-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="742c0-112">Imposta l'identificatore del token per una sottoscrizione a questo oggetto `IDefinitionAppId` sul valore stringa specificato.</span><span class="sxs-lookup"><span data-stu-id="742c0-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="742c0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="742c0-113">Requirements</span></span>  
 <span data-ttu-id="742c0-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="742c0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="742c0-115">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="742c0-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="742c0-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="742c0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="742c0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="742c0-117">See also</span></span>

- [<span data-ttu-id="742c0-118">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="742c0-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
