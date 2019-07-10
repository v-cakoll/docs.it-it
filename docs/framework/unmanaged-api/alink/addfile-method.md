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
ms.openlocfilehash: 7ff6bde5009e834bfca156fe4d3ad16da53ded85
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742390"
---
# <a name="addfile-method"></a><span data-ttu-id="c0fa1-102">Metodo AddFile</span><span class="sxs-lookup"><span data-stu-id="c0fa1-102">AddFile Method</span></span>
<span data-ttu-id="c0fa1-103">Aggiunge i file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-103">Adds files to the assembly.</span></span> <span data-ttu-id="c0fa1-104">È anche utilizzabile per creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0fa1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0fa1-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0fa1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0fa1-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c0fa1-107">ID univoco dell'assembly da essere ampliata.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="c0fa1-108">Nome completo del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c0fa1-109">Flag, ad esempio COM+ FileDef `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="c0fa1-110">`dwFlags` viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="c0fa1-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="c0fa1-111">[Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia da utilizzare per la creazione dei metadati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="c0fa1-112">Puntatore a dove verrà archiviata l'ID univoco del file aggiunto.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0fa1-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c0fa1-113">Return Value</span></span>  
 <span data-ttu-id="c0fa1-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0fa1-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0fa1-115">Requirements</span></span>  
 <span data-ttu-id="c0fa1-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="c0fa1-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0fa1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0fa1-117">See also</span></span>

- [<span data-ttu-id="c0fa1-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c0fa1-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c0fa1-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c0fa1-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c0fa1-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="c0fa1-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
