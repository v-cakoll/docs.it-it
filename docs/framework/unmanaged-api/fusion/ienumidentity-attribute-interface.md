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
ms.openlocfilehash: 7e6bc57fb470a5c12549bb5f9445ecf1551425a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107833"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="c892f-102">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="c892f-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="c892f-103">Funge da enumeratore per gli attributi dell'oggetto di codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="c892f-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c892f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c892f-104">Methods</span></span>  
  
|<span data-ttu-id="c892f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c892f-105">Method</span></span>|<span data-ttu-id="c892f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c892f-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="c892f-107">Ottiene un puntatore a interfaccia per un nuovo `IEnumIDENTITY_ATTRIBUTE` contenente gli stessi membri di questo `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="c892f-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="c892f-108">Scrive i dati contenuti negli elementi di questa `IEnumIDENTITY_ATTRIBUTE` nel buffer dei dati specificato.</span><span class="sxs-lookup"><span data-stu-id="c892f-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="c892f-109">Ottiene il numero specificato di attributi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="c892f-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="c892f-110">Sposta il puntatore all'istruzione all'inizio di questo `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="c892f-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="c892f-111">Sposta il puntatore all'istruzione in poi in base al numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="c892f-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c892f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c892f-112">Requirements</span></span>  
 <span data-ttu-id="c892f-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c892f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c892f-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="c892f-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c892f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c892f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c892f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c892f-116">See also</span></span>

- [<span data-ttu-id="c892f-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="c892f-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
