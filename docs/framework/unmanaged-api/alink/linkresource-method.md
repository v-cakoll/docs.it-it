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
ms.openlocfilehash: 763b7a776007c2ce8dac42c6a5f7f00f6eb58a10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776950"
---
# <a name="linkresource-method"></a><span data-ttu-id="70314-102">Metodo LinkResource</span><span class="sxs-lookup"><span data-stu-id="70314-102">LinkResource Method</span></span>
<span data-ttu-id="70314-103">Collegamenti in una risorsa.</span><span class="sxs-lookup"><span data-stu-id="70314-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70314-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70314-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="70314-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="70314-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="70314-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="70314-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="70314-107">Nome del file.</span><span class="sxs-lookup"><span data-stu-id="70314-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="70314-108">Nuovo nome file facoltativo.</span><span class="sxs-lookup"><span data-stu-id="70314-108">Optional new file name.</span></span> <span data-ttu-id="70314-109">Se diverso da null, `pszFileName` verrà copiato in pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="70314-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="70314-110">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="70314-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="70314-111">Flag di accessibilità `mrPublic` , `mrPrivate`ad esempio e.</span><span class="sxs-lookup"><span data-stu-id="70314-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="70314-112">Questo parametro può essere passato al [metodo DefineManifestResource](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="70314-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70314-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="70314-113">Return Value</span></span>  
 <span data-ttu-id="70314-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="70314-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70314-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="70314-115">Requirements</span></span>  
 <span data-ttu-id="70314-116">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="70314-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70314-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70314-117">See also</span></span>

- [<span data-ttu-id="70314-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="70314-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="70314-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="70314-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="70314-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="70314-120">ALink API</span></span>](index.md)
