---
title: Metodo IMetaDataTables::GetTableIndex
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetTableIndex
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d49e1258011d68a6278d1c40500386024a2cb0d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="47eaa-102">Metodo IMetaDataTables::GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="47eaa-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="47eaa-103">Ottiene l'indice per la tabella a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="47eaa-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47eaa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47eaa-104">Syntax</span></span>  
  
```  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47eaa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="47eaa-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="47eaa-106">[in] Token che fa riferimento alla tabella.</span><span class="sxs-lookup"><span data-stu-id="47eaa-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="47eaa-107">[out] Un puntatore all'indice restituito per la tabella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="47eaa-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47eaa-108">Note</span><span class="sxs-lookup"><span data-stu-id="47eaa-108">Remarks</span></span>  
 <span data-ttu-id="47eaa-109">Non è consigliabile l'utilizzo di questo metodo, perché non restituisce risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="47eaa-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="47eaa-110">Per informazioni sulla tabella dei GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "partizione II: metadati definizione e la semantica".</span><span class="sxs-lookup"><span data-stu-id="47eaa-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="47eaa-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.</span><span class="sxs-lookup"><span data-stu-id="47eaa-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47eaa-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47eaa-112">Requirements</span></span>  
 <span data-ttu-id="47eaa-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47eaa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47eaa-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="47eaa-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47eaa-115">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47eaa-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47eaa-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47eaa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47eaa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47eaa-117">See Also</span></span>  
 [<span data-ttu-id="47eaa-118">IMetaDataTables (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="47eaa-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="47eaa-119">IMetaDataTables2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="47eaa-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
