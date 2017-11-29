---
title: Interfaccia IEnumIDENTITY_ATTRIBUTE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumIDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords: IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f88e400556421e0908e0a0b115f66ec3221124c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="be7d7-102">Interfaccia IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="be7d7-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="be7d7-103">Funge da un enumeratore per gli attributi dell'oggetto codice nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="be7d7-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be7d7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="be7d7-104">Methods</span></span>  
  
|<span data-ttu-id="be7d7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="be7d7-105">Method</span></span>|<span data-ttu-id="be7d7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be7d7-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="be7d7-107">Ottiene un puntatore a interfaccia a un nuovo `IEnumIDENTITY_ATTRIBUTE` che contiene gli stessi membri di questo `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="be7d7-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="be7d7-108">Scrive i dati contenuti negli elementi di questo `IEnumIDENTITY_ATTRIBUTE` al buffer di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="be7d7-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="be7d7-109">Ottiene il numero specificato di attributi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="be7d7-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="be7d7-110">Sposta il puntatore all'istruzione all'inizio di questo `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="be7d7-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="be7d7-111">Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="be7d7-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be7d7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be7d7-112">Requirements</span></span>  
 <span data-ttu-id="be7d7-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be7d7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be7d7-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="be7d7-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="be7d7-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be7d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be7d7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be7d7-116">See Also</span></span>  
 [<span data-ttu-id="be7d7-117">Fusion (interfacce)</span><span class="sxs-lookup"><span data-stu-id="be7d7-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
