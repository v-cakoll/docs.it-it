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
ms.openlocfilehash: 5f6140e5f85a7ee21773c96a5abdccadaddab92e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777450"
---
# <a name="embedresource-method"></a><span data-ttu-id="14049-102">Metodo EmbedResource</span><span class="sxs-lookup"><span data-stu-id="14049-102">EmbedResource Method</span></span>
<span data-ttu-id="14049-103">Dichiara una risorsa incorporata.</span><span class="sxs-lookup"><span data-stu-id="14049-103">Declares an embedded resource.</span></span> <span data-ttu-id="14049-104">Questo metodo non incorpora effettivamente la risorsa.</span><span class="sxs-lookup"><span data-stu-id="14049-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14049-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14049-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="14049-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="14049-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="14049-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="14049-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="14049-108">Token file o ID assembly del file che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="14049-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="14049-109">Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="14049-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="14049-110">Offset della risorsa da RVA.</span><span class="sxs-lookup"><span data-stu-id="14049-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="14049-111">Flag di accessibilità `mrPublic` , `mrPrivate`ad esempio e.</span><span class="sxs-lookup"><span data-stu-id="14049-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="14049-112">Questi flag possono essere passati al [Metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="14049-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14049-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="14049-113">Return Value</span></span>  
 <span data-ttu-id="14049-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="14049-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14049-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14049-115">Requirements</span></span>  
 <span data-ttu-id="14049-116">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="14049-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14049-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14049-117">See also</span></span>

- [<span data-ttu-id="14049-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="14049-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="14049-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="14049-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="14049-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="14049-120">ALink API</span></span>](index.md)
