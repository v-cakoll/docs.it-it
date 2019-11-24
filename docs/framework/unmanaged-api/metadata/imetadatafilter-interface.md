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
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440172"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="71051-102">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="71051-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="71051-103">Fornisce metodi per contrassegnare e filtrare i token di metadati per evitare la ripetizione di azioni che sono già state eseguite.</span><span class="sxs-lookup"><span data-stu-id="71051-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71051-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="71051-104">Methods</span></span>  
  
|<span data-ttu-id="71051-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="71051-105">Method</span></span>|<span data-ttu-id="71051-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71051-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71051-107">Metodo IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="71051-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="71051-108">Gets a value indicating whether the specified metadata token has been processed.</span><span class="sxs-lookup"><span data-stu-id="71051-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="71051-109">Metodo MarkToken</span><span class="sxs-lookup"><span data-stu-id="71051-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="71051-110">Sets a value indicating that the specified metadata token has been processed.</span><span class="sxs-lookup"><span data-stu-id="71051-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="71051-111">Metodo UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="71051-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="71051-112">Removes the processing marks from all the tokens in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="71051-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71051-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71051-113">Requirements</span></span>  
 <span data-ttu-id="71051-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71051-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71051-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71051-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71051-116">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71051-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71051-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71051-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71051-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71051-118">See also</span></span>

- [<span data-ttu-id="71051-119">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="71051-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
