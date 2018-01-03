---
title: AddFile Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.AddFile
- AddFile
api_location: alink.dll
api_type: COM
f1_keywords: AddFile
helpviewer_keywords: AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 943ff2901ee0888860941e86d589060de729907d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="addfile-method1"></a><span data-ttu-id="3957c-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="3957c-102">AddFile Method1</span></span>
<span data-ttu-id="3957c-103">Aggiunge i file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3957c-103">Adds files to the assembly.</span></span> <span data-ttu-id="3957c-104">Consente inoltre di creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="3957c-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3957c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3957c-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3957c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3957c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3957c-107">ID univoco dell'assembly da essere aumentato.</span><span class="sxs-lookup"><span data-stu-id="3957c-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="3957c-108">Nome completo del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="3957c-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3957c-109">Flag COM+ FileDef quali `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="3957c-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="3957c-110">`dwFlags`viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="3957c-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="3957c-111">[Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia da utilizzare per la creazione dei metadati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="3957c-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="3957c-112">Puntatore a dove verrà archiviata l'ID univoco del file aggiunto.</span><span class="sxs-lookup"><span data-stu-id="3957c-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3957c-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3957c-113">Return Value</span></span>  
 <span data-ttu-id="3957c-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="3957c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3957c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3957c-115">Requirements</span></span>  
 <span data-ttu-id="3957c-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="3957c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3957c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3957c-117">See Also</span></span>  
 [<span data-ttu-id="3957c-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="3957c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="3957c-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="3957c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="3957c-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="3957c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
