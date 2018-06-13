---
title: AddImport Method1
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
ms.openlocfilehash: 98fefc0240f6496a3e7bfb491e27a57e98cfea1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404066"
---
# <a name="addimport-method1"></a><span data-ttu-id="a88e1-102">AddImport Method1</span><span class="sxs-lookup"><span data-stu-id="a88e1-102">AddImport Method1</span></span>
<span data-ttu-id="a88e1-103">Aggiunge le importazioni all'assembly.</span><span class="sxs-lookup"><span data-stu-id="a88e1-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a88e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a88e1-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a88e1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a88e1-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a88e1-106">ID univoco dell'assembly da ampliare.</span><span class="sxs-lookup"><span data-stu-id="a88e1-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="a88e1-107">ID univoco, recuperato dal [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del file da importare.</span><span class="sxs-lookup"><span data-stu-id="a88e1-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a88e1-108">Flag COM+ FileDef quali `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="a88e1-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="a88e1-109">`dwFlags` viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="a88e1-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="a88e1-110">Puntatore al token che riceve l'ID per il file risultante.</span><span class="sxs-lookup"><span data-stu-id="a88e1-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a88e1-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a88e1-111">Return Value</span></span>  
 <span data-ttu-id="a88e1-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="a88e1-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a88e1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a88e1-113">Requirements</span></span>  
 <span data-ttu-id="a88e1-114">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="a88e1-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a88e1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a88e1-115">See Also</span></span>  
 [<span data-ttu-id="a88e1-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="a88e1-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a88e1-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="a88e1-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a88e1-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="a88e1-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
