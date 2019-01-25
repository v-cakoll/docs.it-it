---
title: Interfaccia IMetaDataEmit2
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e0477adb4958a53289cd0a64f39259403fa7dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656934"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="6646b-102">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6646b-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="6646b-103">Estende la [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia principalmente per fornire la possibilità di lavorare con i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="6646b-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6646b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6646b-104">Methods</span></span>  
  
|<span data-ttu-id="6646b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6646b-105">Method</span></span>|<span data-ttu-id="6646b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6646b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6646b-107">Metodo DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="6646b-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="6646b-108">Crea una definizione per un parametro di tipo generico e ottiene un token per tale parametro di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="6646b-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="6646b-109">Metodo DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="6646b-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="6646b-110">Crea un'istanza generica di un metodo e ottiene un token per la definizione.</span><span class="sxs-lookup"><span data-stu-id="6646b-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="6646b-111">Metodo GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="6646b-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="6646b-112">Ottiene un valore che indica la differenza nelle dimensione dei dati necessarie per esprimere le modifiche per la sessione corrente di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="6646b-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="6646b-113">Metodo ResetENCLog</span><span class="sxs-lookup"><span data-stu-id="6646b-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="6646b-114">Reimposta il log di modifica e continuazione e avvia una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="6646b-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="6646b-115">Metodo SaveDelta</span><span class="sxs-lookup"><span data-stu-id="6646b-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="6646b-116">Salva le modifiche dalla sessione corrente di modifica e continuazione per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="6646b-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="6646b-117">Metodo SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="6646b-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="6646b-118">Salva le modifiche dalla sessione corrente di modifica e continuazione per la memoria.</span><span class="sxs-lookup"><span data-stu-id="6646b-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="6646b-119">Metodo SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="6646b-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="6646b-120">Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.</span><span class="sxs-lookup"><span data-stu-id="6646b-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="6646b-121">Metodo SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="6646b-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="6646b-122">Imposta i valori di proprietà per la definizione di parametro generico a cui fanno riferimento al token specificato.</span><span class="sxs-lookup"><span data-stu-id="6646b-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6646b-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6646b-123">Requirements</span></span>  
 <span data-ttu-id="6646b-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6646b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6646b-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6646b-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6646b-126">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6646b-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6646b-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6646b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6646b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6646b-128">See also</span></span>
- [<span data-ttu-id="6646b-129">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="6646b-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="6646b-130">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6646b-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
