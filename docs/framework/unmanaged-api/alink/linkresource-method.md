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
ms.openlocfilehash: 9e91d990a8f23335248043c59eb210e8c4155e3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445625"
---
# <a name="linkresource-method"></a><span data-ttu-id="c75b1-102">Metodo LinkResource</span><span class="sxs-lookup"><span data-stu-id="c75b1-102">LinkResource Method</span></span>
<span data-ttu-id="c75b1-103">Collegamenti in una risorsa.</span><span class="sxs-lookup"><span data-stu-id="c75b1-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c75b1-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c75b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c75b1-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c75b1-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c75b1-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="c75b1-107">Nome del file.</span><span class="sxs-lookup"><span data-stu-id="c75b1-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="c75b1-108">Nuovo nome file facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c75b1-108">Optional new file name.</span></span> <span data-ttu-id="c75b1-109">Se non è NULL, `pszFileName` verrà copiato in pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="c75b1-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="c75b1-110">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="c75b1-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c75b1-111">Flag di accessibilità, ad esempio `mrPublic` e `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="c75b1-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="c75b1-112">Questo parametro può essere passato al [metodo DefineManifestResource](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="c75b1-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c75b1-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c75b1-113">Return Value</span></span>  
 <span data-ttu-id="c75b1-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c75b1-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c75b1-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c75b1-115">Requirements</span></span>  
 <span data-ttu-id="c75b1-116">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="c75b1-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75b1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c75b1-117">See also</span></span>

- [<span data-ttu-id="c75b1-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c75b1-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c75b1-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c75b1-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c75b1-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="c75b1-120">ALink API</span></span>](index.md)
