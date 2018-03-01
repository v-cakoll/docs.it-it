---
title: Metodo EmbedResource
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
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 815e4b6abbb56b0998a12c096f0ba7cb678778ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="embedresource-method"></a><span data-ttu-id="23415-102">Metodo EmbedResource</span><span class="sxs-lookup"><span data-stu-id="23415-102">EmbedResource Method</span></span>
<span data-ttu-id="23415-103">Dichiara una risorsa incorporata.</span><span class="sxs-lookup"><span data-stu-id="23415-103">Declares an embedded resource.</span></span> <span data-ttu-id="23415-104">Questo metodo non incorpora la risorsa.</span><span class="sxs-lookup"><span data-stu-id="23415-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23415-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23415-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23415-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="23415-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="23415-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="23415-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="23415-108">Token o assembly ID del file che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="23415-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="23415-109">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="23415-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="23415-110">Offset della risorsa da RVA.</span><span class="sxs-lookup"><span data-stu-id="23415-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="23415-111">Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="23415-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="23415-112">Questi flag possono essere passati a [DefineExportedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="23415-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23415-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23415-113">Return Value</span></span>  
 <span data-ttu-id="23415-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="23415-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23415-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23415-115">Requirements</span></span>  
 <span data-ttu-id="23415-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="23415-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23415-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23415-117">See Also</span></span>  
 [<span data-ttu-id="23415-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="23415-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="23415-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="23415-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="23415-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="23415-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
