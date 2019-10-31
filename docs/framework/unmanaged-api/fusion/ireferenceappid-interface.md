---
title: Interfaccia IReferenceAppId
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131656"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="db64c-102">Interfaccia IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="db64c-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="db64c-103">Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="db64c-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db64c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="db64c-104">Methods</span></span>  
  
|<span data-ttu-id="db64c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="db64c-105">Method</span></span>|<span data-ttu-id="db64c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db64c-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="db64c-107">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="db64c-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="db64c-108">Imposta l'identificatore del codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="db64c-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="db64c-109">Ottiene un puntatore a interfaccia a un'istanza `IEnumReferenceIdentity` contenente le istanze di `IReferenceIdentity` che rappresentano i membri di questa `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="db64c-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="db64c-110">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione a questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="db64c-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="db64c-111">Imposta l'identificatore del token per una sottoscrizione di questo `IReferenceAppId` sul valore stringa specificato.</span><span class="sxs-lookup"><span data-stu-id="db64c-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db64c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db64c-112">Requirements</span></span>  
 <span data-ttu-id="db64c-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db64c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db64c-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="db64c-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="db64c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db64c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db64c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db64c-116">See also</span></span>

- [<span data-ttu-id="db64c-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="db64c-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="db64c-118">Interfaccia IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="db64c-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="db64c-119">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="db64c-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
