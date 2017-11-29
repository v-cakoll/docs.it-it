---
title: Interfaccia IMetaDataFilter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter
helpviewer_keywords: IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7c0afbb9be9af3ffe69ddfcac85b70de53a391ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="a6979-102">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="a6979-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="a6979-103">Fornisce metodi per contrassegnare e filtrare i token di metadati per evitare la ripetizione di azioni che sono già state eseguite.</span><span class="sxs-lookup"><span data-stu-id="a6979-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6979-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a6979-104">Methods</span></span>  
  
|<span data-ttu-id="a6979-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a6979-105">Method</span></span>|<span data-ttu-id="a6979-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6979-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6979-107">IsTokenMarked (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6979-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="a6979-108">Ottiene un valore che indica se il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="a6979-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="a6979-109">MarkToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6979-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="a6979-110">Imposta un valore che indica che il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="a6979-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="a6979-111">UnmarkAll (metodo)</span><span class="sxs-lookup"><span data-stu-id="a6979-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="a6979-112">Rimuove gli indicatori di elaborazione da tutti i token nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="a6979-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6979-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6979-113">Requirements</span></span>  
 <span data-ttu-id="a6979-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6979-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6979-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6979-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6979-116">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6979-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6979-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6979-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6979-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6979-118">See Also</span></span>  
 [<span data-ttu-id="a6979-119">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="a6979-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
