---
title: Metodo AddImport
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
ms.openlocfilehash: 95a434cc365e12aa19d164951726ddad8945f60d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974133"
---
# <a name="addimport-method"></a><span data-ttu-id="fe300-102">Metodo AddImport</span><span class="sxs-lookup"><span data-stu-id="fe300-102">AddImport Method</span></span>
<span data-ttu-id="fe300-103">Aggiunge le importazioni dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fe300-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe300-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe300-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe300-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe300-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fe300-106">ID univoco dell'assembly da ampliare.</span><span class="sxs-lookup"><span data-stu-id="fe300-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="fe300-107">ID univoco, recuperato dal [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del file da importare.</span><span class="sxs-lookup"><span data-stu-id="fe300-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fe300-108">Flag, ad esempio COM+ FileDef `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="fe300-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="fe300-109">`dwFlags` viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="fe300-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="fe300-110">Puntatore al token che riceve l'ID per il file risultante.</span><span class="sxs-lookup"><span data-stu-id="fe300-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe300-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fe300-111">Return Value</span></span>  
 <span data-ttu-id="fe300-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fe300-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe300-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe300-113">Requirements</span></span>  
 <span data-ttu-id="fe300-114">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="fe300-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe300-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe300-115">See also</span></span>
- [<span data-ttu-id="fe300-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="fe300-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fe300-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="fe300-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fe300-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="fe300-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
