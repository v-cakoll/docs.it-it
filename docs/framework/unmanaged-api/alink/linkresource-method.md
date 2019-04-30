---
title: Metodo LinkResource
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e851c1bd56c0e9ece02fb06c0dcd9975a5b02ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949097"
---
# <a name="linkresource-method"></a><span data-ttu-id="b1772-102">Metodo LinkResource</span><span class="sxs-lookup"><span data-stu-id="b1772-102">LinkResource Method</span></span>
<span data-ttu-id="b1772-103">Collegamenti in una risorsa.</span><span class="sxs-lookup"><span data-stu-id="b1772-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1772-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1772-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1772-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1772-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b1772-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b1772-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="b1772-107">Nome del file.</span><span class="sxs-lookup"><span data-stu-id="b1772-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="b1772-108">Nuovo nome file facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b1772-108">Optional new file name.</span></span> <span data-ttu-id="b1772-109">Se diverso da NULL, `pszFileName` pszNewLocation verranno copiati.</span><span class="sxs-lookup"><span data-stu-id="b1772-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="b1772-110">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="b1772-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b1772-111">Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="b1772-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="b1772-112">Questo parametro può essere passato a [metodo DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="b1772-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1772-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b1772-113">Return Value</span></span>  
 <span data-ttu-id="b1772-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b1772-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1772-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1772-115">Requirements</span></span>  
 <span data-ttu-id="b1772-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="b1772-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1772-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1772-117">See also</span></span>

- [<span data-ttu-id="b1772-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b1772-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b1772-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b1772-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b1772-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="b1772-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
