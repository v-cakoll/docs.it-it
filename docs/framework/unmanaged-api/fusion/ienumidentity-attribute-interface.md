---
title: Interfaccia IEnumIDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d725228f2a7359d415673fdcb90d0cabae1a40be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175526"
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="3a18c-102">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="3a18c-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="3a18c-103">Funge da un enumeratore per gli attributi dell'oggetto codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="3a18c-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a18c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3a18c-104">Methods</span></span>  
  
|<span data-ttu-id="3a18c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3a18c-105">Method</span></span>|<span data-ttu-id="3a18c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a18c-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="3a18c-107">Ottiene un puntatore a interfaccia a una nuova `IEnumIDENTITY_ATTRIBUTE` che contiene gli stessi membri di questo `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="3a18c-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="3a18c-108">Scrive i dati contenuti negli elementi di questo `IEnumIDENTITY_ATTRIBUTE` al buffer di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="3a18c-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="3a18c-109">Ottiene il numero specificato di attributi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="3a18c-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="3a18c-110">Sposta il puntatore all'istruzione all'inizio di questo `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="3a18c-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="3a18c-111">Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="3a18c-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a18c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a18c-112">Requirements</span></span>  
 <span data-ttu-id="3a18c-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a18c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a18c-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="3a18c-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="3a18c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a18c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a18c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a18c-116">See also</span></span>

- [<span data-ttu-id="3a18c-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="3a18c-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
