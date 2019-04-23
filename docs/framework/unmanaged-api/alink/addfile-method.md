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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162215"
---
# <a name="addfile-method"></a><span data-ttu-id="1da8b-102">Metodo AddFile</span><span class="sxs-lookup"><span data-stu-id="1da8b-102">AddFile Method</span></span>
<span data-ttu-id="1da8b-103">Aggiunge i file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1da8b-103">Adds files to the assembly.</span></span> <span data-ttu-id="1da8b-104">È anche utilizzabile per creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="1da8b-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1da8b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1da8b-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1da8b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1da8b-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1da8b-107">ID univoco dell'assembly da essere ampliata.</span><span class="sxs-lookup"><span data-stu-id="1da8b-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="1da8b-108">Nome completo del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1da8b-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1da8b-109">Flag, ad esempio COM+ FileDef `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="1da8b-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="1da8b-110">`dwFlags` viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="1da8b-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="1da8b-111">[Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia da utilizzare per la creazione dei metadati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="1da8b-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="1da8b-112">Puntatore a dove verrà archiviata l'ID univoco del file aggiunto.</span><span class="sxs-lookup"><span data-stu-id="1da8b-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1da8b-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1da8b-113">Return Value</span></span>  
 <span data-ttu-id="1da8b-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1da8b-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1da8b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1da8b-115">Requirements</span></span>  
 <span data-ttu-id="1da8b-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="1da8b-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da8b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1da8b-117">See also</span></span>

- [<span data-ttu-id="1da8b-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="1da8b-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1da8b-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="1da8b-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1da8b-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="1da8b-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
