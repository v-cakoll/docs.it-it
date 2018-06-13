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
ms.openlocfilehash: ad77aba02c819749794534ca2ecd478661bc363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444981"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="c6010-102">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="c6010-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="c6010-103">Fornisce metodi per contrassegnare e filtrare i token di metadati per evitare la ripetizione di azioni che sono già state eseguite.</span><span class="sxs-lookup"><span data-stu-id="c6010-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6010-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c6010-104">Methods</span></span>  
  
|<span data-ttu-id="c6010-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c6010-105">Method</span></span>|<span data-ttu-id="c6010-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6010-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6010-107">Metodo IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="c6010-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="c6010-108">Ottiene un valore che indica se il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="c6010-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="c6010-109">Metodo MarkToken</span><span class="sxs-lookup"><span data-stu-id="c6010-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="c6010-110">Imposta un valore che indica che il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="c6010-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="c6010-111">Metodo UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="c6010-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="c6010-112">Rimuove gli indicatori di elaborazione da tutti i token nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="c6010-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6010-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6010-113">Requirements</span></span>  
 <span data-ttu-id="c6010-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6010-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6010-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c6010-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6010-116">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c6010-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6010-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6010-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6010-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6010-118">See Also</span></span>  
 [<span data-ttu-id="c6010-119">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="c6010-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
