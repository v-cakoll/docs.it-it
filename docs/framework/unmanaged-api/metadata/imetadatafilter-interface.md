---
title: Interfaccia IMetaDataFilter
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: 821936d20a421739e8eb3d5df228888df7f022e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503783"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="0b07d-102">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="0b07d-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="0b07d-103">Fornisce metodi per contrassegnare e filtrare i token di metadati per evitare la ripetizione di azioni che sono già state eseguite.</span><span class="sxs-lookup"><span data-stu-id="0b07d-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b07d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0b07d-104">Methods</span></span>  
  
|<span data-ttu-id="0b07d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0b07d-105">Method</span></span>|<span data-ttu-id="0b07d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b07d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b07d-107">Metodo IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="0b07d-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="0b07d-108">Ottiene un valore che indica se il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="0b07d-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="0b07d-109">Metodo MarkToken</span><span class="sxs-lookup"><span data-stu-id="0b07d-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="0b07d-110">Imposta un valore che indica che il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="0b07d-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="0b07d-111">Metodo UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="0b07d-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="0b07d-112">Rimuove i contrassegni di elaborazione da tutti i token nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="0b07d-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b07d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b07d-113">Requirements</span></span>  
 <span data-ttu-id="0b07d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b07d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b07d-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0b07d-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b07d-116">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0b07d-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b07d-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b07d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b07d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b07d-118">See also</span></span>

- [<span data-ttu-id="0b07d-119">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="0b07d-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
