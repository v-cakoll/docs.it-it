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
ms.openlocfilehash: 8cb1f985c1d735fa20507ab90d478e97025c9e2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-method"></a><span data-ttu-id="60cfd-102">Metodo LinkResource</span><span class="sxs-lookup"><span data-stu-id="60cfd-102">LinkResource Method</span></span>
<span data-ttu-id="60cfd-103">Collegamenti in una risorsa.</span><span class="sxs-lookup"><span data-stu-id="60cfd-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60cfd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60cfd-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60cfd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60cfd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="60cfd-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="60cfd-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="60cfd-107">Nome del file.</span><span class="sxs-lookup"><span data-stu-id="60cfd-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="60cfd-108">Nuovo nome file facoltativo.</span><span class="sxs-lookup"><span data-stu-id="60cfd-108">Optional new file name.</span></span> <span data-ttu-id="60cfd-109">Se diverso da NULL, `pszFileName` pszNewLocation verranno copiati.</span><span class="sxs-lookup"><span data-stu-id="60cfd-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="60cfd-110">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="60cfd-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="60cfd-111">Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="60cfd-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="60cfd-112">Questo parametro può essere passato a [DefineManifestResource (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="60cfd-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60cfd-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="60cfd-113">Return Value</span></span>  
 <span data-ttu-id="60cfd-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="60cfd-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60cfd-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60cfd-115">Requirements</span></span>  
 <span data-ttu-id="60cfd-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="60cfd-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60cfd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60cfd-117">See Also</span></span>  
 [<span data-ttu-id="60cfd-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="60cfd-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="60cfd-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="60cfd-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="60cfd-120">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="60cfd-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
