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
ms.openlocfilehash: ef7d6272c04c3edab8ef652bcb2759861ff2b982
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790052"
---
# <a name="embedresource-method"></a><span data-ttu-id="e9248-102">Metodo EmbedResource</span><span class="sxs-lookup"><span data-stu-id="e9248-102">EmbedResource Method</span></span>
<span data-ttu-id="e9248-103">Dichiara una risorsa incorporata.</span><span class="sxs-lookup"><span data-stu-id="e9248-103">Declares an embedded resource.</span></span> <span data-ttu-id="e9248-104">Questo metodo non consente di incorporare effettivamente la risorsa.</span><span class="sxs-lookup"><span data-stu-id="e9248-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9248-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9248-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9248-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9248-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e9248-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e9248-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e9248-108">Assembly o token ID di file che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="e9248-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="e9248-109">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="e9248-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="e9248-110">Offset della risorsa da RVA.</span><span class="sxs-lookup"><span data-stu-id="e9248-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e9248-111">Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="e9248-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="e9248-112">Questi flag possono essere passati a [metodo DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="e9248-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9248-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e9248-113">Return Value</span></span>  
 <span data-ttu-id="e9248-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e9248-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9248-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9248-115">Requirements</span></span>  
 <span data-ttu-id="e9248-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="e9248-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9248-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9248-117">See also</span></span>

- [<span data-ttu-id="e9248-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e9248-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e9248-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e9248-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e9248-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="e9248-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
