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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4196ff2cb2d4ebc401076f603a8a7fdc9b9c76ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049960"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="28abc-102">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="28abc-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="28abc-103">Fornisce metodi per contrassegnare e filtrare i token di metadati per evitare la ripetizione di azioni che sono già state eseguite.</span><span class="sxs-lookup"><span data-stu-id="28abc-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28abc-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="28abc-104">Methods</span></span>  
  
|<span data-ttu-id="28abc-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="28abc-105">Method</span></span>|<span data-ttu-id="28abc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28abc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28abc-107">Metodo IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="28abc-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="28abc-108">Ottiene un valore che indica se il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="28abc-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="28abc-109">Metodo MarkToken</span><span class="sxs-lookup"><span data-stu-id="28abc-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="28abc-110">Imposta un valore che indica che il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="28abc-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="28abc-111">Metodo UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="28abc-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="28abc-112">Rimuove i segni di elaborazione da tutti i token nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="28abc-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28abc-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28abc-113">Requirements</span></span>  
 <span data-ttu-id="28abc-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28abc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28abc-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="28abc-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28abc-116">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="28abc-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28abc-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28abc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28abc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28abc-118">See also</span></span>

- [<span data-ttu-id="28abc-119">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="28abc-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
