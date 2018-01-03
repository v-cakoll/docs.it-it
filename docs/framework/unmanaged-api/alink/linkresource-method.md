---
title: Metodo LinkResource
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.LinkResource
api_location: alink.dll
api_type: COM
f1_keywords: LinkResource
helpviewer_keywords: LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1ff38bf0017cf400d8f35f0ddf265f8628c82d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="linkresource-method"></a><span data-ttu-id="e6aab-102">Metodo LinkResource</span><span class="sxs-lookup"><span data-stu-id="e6aab-102">LinkResource Method</span></span>
<span data-ttu-id="e6aab-103">Collegamenti in una risorsa.</span><span class="sxs-lookup"><span data-stu-id="e6aab-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6aab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6aab-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6aab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6aab-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e6aab-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e6aab-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="e6aab-107">Nome del file.</span><span class="sxs-lookup"><span data-stu-id="e6aab-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="e6aab-108">Nuovo nome file facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e6aab-108">Optional new file name.</span></span> <span data-ttu-id="e6aab-109">Se diverso da NULL, `pszFileName` pszNewLocation verranno copiati.</span><span class="sxs-lookup"><span data-stu-id="e6aab-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="e6aab-110">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="e6aab-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e6aab-111">Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="e6aab-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="e6aab-112">Questo parametro può essere passato a [DefineManifestResource (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="e6aab-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6aab-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e6aab-113">Return Value</span></span>  
 <span data-ttu-id="e6aab-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="e6aab-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6aab-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6aab-115">Requirements</span></span>  
 <span data-ttu-id="e6aab-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="e6aab-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6aab-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6aab-117">See Also</span></span>  
 [<span data-ttu-id="e6aab-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e6aab-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e6aab-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e6aab-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e6aab-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="e6aab-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
