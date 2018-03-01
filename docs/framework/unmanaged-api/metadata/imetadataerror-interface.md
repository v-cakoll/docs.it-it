---
title: Interfaccia IMetaDataError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4df7aa7400a180151de5420effc8738955d51c26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="ae3f8-102">Interfaccia IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="ae3f8-102">IMetaDataError Interface</span></span>
<span data-ttu-id="ae3f8-103">Fornisce un meccanismo di callback per la segnalazione di errori durante il merge dei metadati.</span><span class="sxs-lookup"><span data-stu-id="ae3f8-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae3f8-104">Il `IMetaDataError` interfaccia deve essere implementata dal client.</span><span class="sxs-lookup"><span data-stu-id="ae3f8-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae3f8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ae3f8-105">Methods</span></span>  
  
|<span data-ttu-id="ae3f8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ae3f8-106">Method</span></span>|<span data-ttu-id="ae3f8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae3f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae3f8-108">Metodo OnError</span><span class="sxs-lookup"><span data-stu-id="ae3f8-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="ae3f8-109">Fornisce la notifica degli errori che si verificano durante l'unione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="ae3f8-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae3f8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae3f8-110">Requirements</span></span>  
 <span data-ttu-id="ae3f8-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae3f8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae3f8-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ae3f8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae3f8-113">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae3f8-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae3f8-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae3f8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae3f8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae3f8-115">See Also</span></span>  
 [<span data-ttu-id="ae3f8-116">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="ae3f8-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
