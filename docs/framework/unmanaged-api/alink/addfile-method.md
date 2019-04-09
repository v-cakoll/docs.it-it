---
title: Metodo AddFile
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 056d1ac0ffd3ad7fa7cb1f86ae13331ac38b3eff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162215"
---
# <a name="addfile-method"></a><span data-ttu-id="e8a9a-102">Metodo AddFile</span><span class="sxs-lookup"><span data-stu-id="e8a9a-102">AddFile Method</span></span>
<span data-ttu-id="e8a9a-103">Aggiunge i file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-103">Adds files to the assembly.</span></span> <span data-ttu-id="e8a9a-104">È anche utilizzabile per creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a9a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8a9a-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8a9a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8a9a-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e8a9a-107">ID univoco dell'assembly da essere ampliata.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="e8a9a-108">Nome completo del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e8a9a-109">Flag, ad esempio COM+ FileDef `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> `dwFlags` <span data-ttu-id="e8a9a-110">viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="e8a9a-110">is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="e8a9a-111">[Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia da utilizzare per la creazione dei metadati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="e8a9a-112">Puntatore a dove verrà archiviata l'ID univoco del file aggiunto.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8a9a-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e8a9a-113">Return Value</span></span>  
 <span data-ttu-id="e8a9a-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8a9a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8a9a-115">Requirements</span></span>  
 <span data-ttu-id="e8a9a-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="e8a9a-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a9a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8a9a-117">See also</span></span>

- [<span data-ttu-id="e8a9a-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e8a9a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e8a9a-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e8a9a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e8a9a-120">API Alink</span><span class="sxs-lookup"><span data-stu-id="e8a9a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
