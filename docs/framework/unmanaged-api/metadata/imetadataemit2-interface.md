---
title: Interfaccia IMetaDataEmit2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2
helpviewer_keywords: IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 235134c66395f04a87ed4f3325f5cc4cd9fecfc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="bb3ec-102">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bb3ec-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="bb3ec-103">Estende il [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia principalmente per offrire la possibilità di utilizzare i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb3ec-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="bb3ec-104">Methods</span></span>  
  
|<span data-ttu-id="bb3ec-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="bb3ec-105">Method</span></span>|<span data-ttu-id="bb3ec-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb3ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb3ec-107">DefineGenericParam (metodo)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="bb3ec-108">Crea una definizione per un parametro di tipo generico e ottiene un token per tale parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="bb3ec-109">DefineMethodSpec (metodo)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="bb3ec-110">Crea un'istanza generica di un metodo e ottiene un token per la definizione.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="bb3ec-111">GetDeltaSaveSize (metodo)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="bb3ec-112">Ottiene un valore che indica la differenza nelle dimensioni dei dati che sono necessario per esprimere le modifiche per la sessione di modifica e continuazione corrente.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="bb3ec-113">ResetENCLog (metodo)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="bb3ec-114">Reimposta il log di modifica e continuazione e avvia una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="bb3ec-115">SaveDelta (metodo)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="bb3ec-116">Salva le modifiche dalla sessione di modifica e continuazione corrente nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="bb3ec-117">SaveDeltaToMemory (metodo)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="bb3ec-118">Salva le modifiche dalla sessione corrente di modifica e continuazione in memoria.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="bb3ec-119">SaveDeltaToStream (metodo)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="bb3ec-120">Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="bb3ec-121">SetGenericParamProps (metodo)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="bb3ec-122">Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb3ec-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb3ec-123">Requirements</span></span>  
 <span data-ttu-id="bb3ec-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb3ec-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb3ec-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bb3ec-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb3ec-126">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb3ec-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb3ec-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb3ec-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3ec-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb3ec-128">See Also</span></span>  
 [<span data-ttu-id="bb3ec-129">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="bb3ec-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="bb3ec-130">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
