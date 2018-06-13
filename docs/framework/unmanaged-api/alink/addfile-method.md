---
title: AddFile Method1
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
ms.openlocfilehash: 57a350fadfa77fdad545ca7ccf2f63d28607c2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403920"
---
# <a name="addfile-method1"></a><span data-ttu-id="fe909-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="fe909-102">AddFile Method1</span></span>
<span data-ttu-id="fe909-103">Aggiunge i file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fe909-103">Adds files to the assembly.</span></span> <span data-ttu-id="fe909-104">Consente inoltre di creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="fe909-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe909-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe909-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe909-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe909-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fe909-107">ID univoco dell'assembly da essere aumentato.</span><span class="sxs-lookup"><span data-stu-id="fe909-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="fe909-108">Nome completo del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="fe909-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fe909-109">Flag COM+ FileDef quali `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="fe909-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="fe909-110">`dwFlags` viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="fe909-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="fe909-111">[Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia da utilizzare per generare metadati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="fe909-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="fe909-112">Puntatore a dove verrà archiviata l'ID univoco del file aggiunto.</span><span class="sxs-lookup"><span data-stu-id="fe909-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe909-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fe909-113">Return Value</span></span>  
 <span data-ttu-id="fe909-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="fe909-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe909-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe909-115">Requirements</span></span>  
 <span data-ttu-id="fe909-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="fe909-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe909-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe909-117">See Also</span></span>  
 [<span data-ttu-id="fe909-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="fe909-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="fe909-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="fe909-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="fe909-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="fe909-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
