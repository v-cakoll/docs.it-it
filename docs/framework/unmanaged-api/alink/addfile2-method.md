---
title: Metodo AddFile2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AddFile2
- IALink2.AddFile2
api_location: alink.dll
api_type: COM
f1_keywords: AddFile2
helpviewer_keywords: AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fe10a3ca8930087a52d02905534696dbb2d8fb25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="addfile2-method"></a><span data-ttu-id="ee34c-102">Metodo AddFile2</span><span class="sxs-lookup"><span data-stu-id="ee34c-102">AddFile2 Method</span></span>
<span data-ttu-id="ee34c-103">Aggiunge i file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ee34c-103">Adds files to the assembly.</span></span> <span data-ttu-id="ee34c-104">Consente inoltre di creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="ee34c-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee34c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee34c-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee34c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee34c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ee34c-107">ID dell'assembly a cui viene aggiunto il file.</span><span class="sxs-lookup"><span data-stu-id="ee34c-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="ee34c-108">Nome del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="ee34c-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ee34c-109">COM+ `FileDef` flag come `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="ee34c-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="ee34c-110">`dwFlags`viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="ee34c-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="ee34c-111">Interfaccia [interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ee34c-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="ee34c-112">Riceve l'ID del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="ee34c-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee34c-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ee34c-113">Return Value</span></span>  
 <span data-ttu-id="ee34c-114">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="ee34c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee34c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee34c-115">Requirements</span></span>  
 <span data-ttu-id="ee34c-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="ee34c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee34c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee34c-117">See Also</span></span>  
 [<span data-ttu-id="ee34c-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ee34c-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ee34c-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ee34c-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ee34c-120">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="ee34c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
