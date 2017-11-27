---
title: Metodo EmbedResource
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmbedResource
- EmbedResource
api_location: alink.dll
api_type: COM
f1_keywords: EmbedResource
helpviewer_keywords: EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 98dbd32452184bf4f832bd66ffebb0fcf3d5bb0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="embedresource-method"></a><span data-ttu-id="8fe0d-102">Metodo EmbedResource</span><span class="sxs-lookup"><span data-stu-id="8fe0d-102">EmbedResource Method</span></span>
<span data-ttu-id="8fe0d-103">Dichiara una risorsa incorporata.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-103">Declares an embedded resource.</span></span> <span data-ttu-id="8fe0d-104">Questo metodo non incorpora la risorsa.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe0d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fe0d-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fe0d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fe0d-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8fe0d-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="8fe0d-108">Token o assembly ID del file che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="8fe0d-109">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="8fe0d-110">Offset della risorsa da RVA.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8fe0d-111">Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="8fe0d-112">Questi flag possono essere passati a [DefineExportedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="8fe0d-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fe0d-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8fe0d-113">Return Value</span></span>  
 <span data-ttu-id="8fe0d-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fe0d-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fe0d-115">Requirements</span></span>  
 <span data-ttu-id="8fe0d-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="8fe0d-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe0d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fe0d-117">See Also</span></span>  
 [<span data-ttu-id="8fe0d-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="8fe0d-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8fe0d-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="8fe0d-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8fe0d-120">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="8fe0d-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
