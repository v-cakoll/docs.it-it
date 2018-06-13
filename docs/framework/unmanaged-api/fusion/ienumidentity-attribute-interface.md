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
ms.openlocfilehash: da6462a320b1f090940473f566ade91d36e74780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431701"
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="6b8f4-102">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="6b8f4-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="6b8f4-103">Funge da un enumeratore per gli attributi dell'oggetto codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="6b8f4-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b8f4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6b8f4-104">Methods</span></span>  
  
|<span data-ttu-id="6b8f4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6b8f4-105">Method</span></span>|<span data-ttu-id="6b8f4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b8f4-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="6b8f4-107">Ottiene un puntatore a interfaccia a un nuovo `IEnumIDENTITY_ATTRIBUTE` che contiene gli stessi membri di questo `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="6b8f4-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="6b8f4-108">Scrive i dati contenuti negli elementi di questo `IEnumIDENTITY_ATTRIBUTE` al buffer di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="6b8f4-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="6b8f4-109">Ottiene il numero specificato di attributi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="6b8f4-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="6b8f4-110">Sposta il puntatore all'istruzione all'inizio di questo `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="6b8f4-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="6b8f4-111">Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="6b8f4-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b8f4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b8f4-112">Requirements</span></span>  
 <span data-ttu-id="6b8f4-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b8f4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b8f4-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="6b8f4-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6b8f4-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b8f4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8f4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b8f4-116">See Also</span></span>  
 [<span data-ttu-id="6b8f4-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="6b8f4-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
