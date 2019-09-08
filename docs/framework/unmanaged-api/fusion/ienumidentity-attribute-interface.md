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
ms.openlocfilehash: dbb3ac150ebfe9fe3698427d8bb2bfb3e3347c07
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796462"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="107f5-102">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="107f5-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="107f5-103">Funge da enumeratore per gli attributi dell'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="107f5-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="107f5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="107f5-104">Methods</span></span>  
  
|<span data-ttu-id="107f5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="107f5-105">Method</span></span>|<span data-ttu-id="107f5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="107f5-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="107f5-107">Ottiene un puntatore a interfaccia a un `IEnumIDENTITY_ATTRIBUTE` nuovo oggetto che contiene gli stessi membri `IEnumIDENTITY_ATTRIBUTE`di questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="107f5-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="107f5-108">Scrive i dati contenuti negli elementi di questo `IEnumIDENTITY_ATTRIBUTE` oggetto nel buffer di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="107f5-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="107f5-109">Ottiene il numero specificato di attributi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="107f5-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="107f5-110">Sposta il puntatore all'istruzione all'inizio di questo `IEnumIDENTITY_ATTRIBUTE`oggetto.</span><span class="sxs-lookup"><span data-stu-id="107f5-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="107f5-111">Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="107f5-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="107f5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="107f5-112">Requirements</span></span>  
 <span data-ttu-id="107f5-113">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="107f5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="107f5-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="107f5-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="107f5-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="107f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="107f5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="107f5-116">See also</span></span>

- [<span data-ttu-id="107f5-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="107f5-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
