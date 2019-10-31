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
ms.openlocfilehash: 59578e1d3a66809c86f7daad1b208df2ae09568d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108035"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="24943-102">Interfaccia IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="24943-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="24943-103">Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="24943-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24943-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="24943-104">Methods</span></span>  
  
|<span data-ttu-id="24943-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="24943-105">Method</span></span>|<span data-ttu-id="24943-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24943-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="24943-107">Ottiene un puntatore a interfaccia a un nuovo oggetto `IDefinitionIdentity` identico a questo `IDefinitionIdentity`, ad eccezione delle modifiche di attributo specificate.</span><span class="sxs-lookup"><span data-stu-id="24943-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="24943-108">Ottiene un puntatore a interfaccia a un oggetto [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) che contiene gli attributi associati a questo `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="24943-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="24943-109">Ottiene il valore dell'attributo con il nome specificato nello spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="24943-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="24943-110">Imposta l'attributo con il nome specificato nello spazio dei nomi specificato sul valore specificato.</span><span class="sxs-lookup"><span data-stu-id="24943-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24943-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24943-111">Requirements</span></span>  
 <span data-ttu-id="24943-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24943-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24943-113">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="24943-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="24943-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24943-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24943-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24943-115">See also</span></span>

- [<span data-ttu-id="24943-116">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="24943-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
