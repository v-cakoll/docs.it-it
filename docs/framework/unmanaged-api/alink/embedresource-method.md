---
title: Metodo EmbedResource
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af5a200578c34464b5f8d86e568d08d814b46a29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742151"
---
# <a name="embedresource-method"></a><span data-ttu-id="32296-102">Metodo EmbedResource</span><span class="sxs-lookup"><span data-stu-id="32296-102">EmbedResource Method</span></span>
<span data-ttu-id="32296-103">Dichiara una risorsa incorporata.</span><span class="sxs-lookup"><span data-stu-id="32296-103">Declares an embedded resource.</span></span> <span data-ttu-id="32296-104">Questo metodo non consente di incorporare effettivamente la risorsa.</span><span class="sxs-lookup"><span data-stu-id="32296-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32296-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32296-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="32296-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="32296-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="32296-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="32296-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="32296-108">Assembly o token ID di file che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="32296-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="32296-109">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="32296-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="32296-110">Offset della risorsa da RVA.</span><span class="sxs-lookup"><span data-stu-id="32296-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="32296-111">Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="32296-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="32296-112">Questi flag possono essere passati a [metodo DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="32296-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32296-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="32296-113">Return Value</span></span>  
 <span data-ttu-id="32296-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="32296-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32296-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32296-115">Requirements</span></span>  
 <span data-ttu-id="32296-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="32296-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32296-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32296-117">See also</span></span>

- [<span data-ttu-id="32296-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="32296-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="32296-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="32296-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="32296-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="32296-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
