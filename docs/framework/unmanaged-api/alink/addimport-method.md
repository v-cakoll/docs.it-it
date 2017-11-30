---
title: AddImport Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AddImport
- IALink.AddImport
api_location: alink.dll
api_type: COM
f1_keywords: AddImport
helpviewer_keywords: AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd0e55cab6f0fdb7f971d7cf06e5703340e32307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="addimport-method1"></a><span data-ttu-id="d461b-102">AddImport Method1</span><span class="sxs-lookup"><span data-stu-id="d461b-102">AddImport Method1</span></span>
<span data-ttu-id="d461b-103">Aggiunge le importazioni all'assembly.</span><span class="sxs-lookup"><span data-stu-id="d461b-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d461b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d461b-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d461b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d461b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d461b-106">ID univoco dell'assembly da ampliare.</span><span class="sxs-lookup"><span data-stu-id="d461b-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="d461b-107">ID univoco, recuperato dal [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del file da importare.</span><span class="sxs-lookup"><span data-stu-id="d461b-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d461b-108">Flag COM+ FileDef quali `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="d461b-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="d461b-109">`dwFlags`viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="d461b-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="d461b-110">Puntatore al token che riceve l'ID per il file risultante.</span><span class="sxs-lookup"><span data-stu-id="d461b-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d461b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d461b-111">Return Value</span></span>  
 <span data-ttu-id="d461b-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="d461b-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d461b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d461b-113">Requirements</span></span>  
 <span data-ttu-id="d461b-114">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="d461b-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d461b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d461b-115">See Also</span></span>  
 [<span data-ttu-id="d461b-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d461b-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d461b-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d461b-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d461b-118">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="d461b-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
