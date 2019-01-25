---
title: Metodo1 AddImport
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d2daed0450e04137621788e830bbedb467bd57c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706339"
---
# <a name="addimport-method1"></a><span data-ttu-id="5abda-102">Metodo1 AddImport</span><span class="sxs-lookup"><span data-stu-id="5abda-102">AddImport Method1</span></span>
<span data-ttu-id="5abda-103">Aggiunge le importazioni dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5abda-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5abda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5abda-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5abda-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5abda-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5abda-106">ID univoco dell'assembly da ampliare.</span><span class="sxs-lookup"><span data-stu-id="5abda-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="5abda-107">ID univoco, recuperato dal [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del file da importare.</span><span class="sxs-lookup"><span data-stu-id="5abda-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5abda-108">Flag, ad esempio COM+ FileDef `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="5abda-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="5abda-109">`dwFlags` viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="5abda-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="5abda-110">Puntatore al token che riceve l'ID per il file risultante.</span><span class="sxs-lookup"><span data-stu-id="5abda-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5abda-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5abda-111">Return Value</span></span>  
 <span data-ttu-id="5abda-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5abda-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5abda-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5abda-113">Requirements</span></span>  
 <span data-ttu-id="5abda-114">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="5abda-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5abda-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5abda-115">See also</span></span>
- [<span data-ttu-id="5abda-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="5abda-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5abda-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="5abda-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5abda-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="5abda-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
