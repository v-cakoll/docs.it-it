---
title: Metodo AddFile2
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 078820649543479e65ec35daa6e1cc2876581ddc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693201"
---
# <a name="addfile2-method"></a><span data-ttu-id="1ea6c-102">Metodo AddFile2</span><span class="sxs-lookup"><span data-stu-id="1ea6c-102">AddFile2 Method</span></span>
<span data-ttu-id="1ea6c-103">Aggiunge i file dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-103">Adds files to the assembly.</span></span> <span data-ttu-id="1ea6c-104">È anche utilizzabile per creare moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ea6c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ea6c-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ea6c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1ea6c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1ea6c-107">ID dell'assembly a cui il file viene aggiunto.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="1ea6c-108">Nome del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1ea6c-109">COM+ `FileDef` , ad esempio i flag `ffContainsNoMetaData` e `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="1ea6c-110">`dwFlags` viene passato a [metodo DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="1ea6c-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="1ea6c-111">Interfaccia per l'interfaccia [interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="1ea6c-112">Riceve l'ID del file da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ea6c-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1ea6c-113">Return Value</span></span>  
 <span data-ttu-id="1ea6c-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ea6c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ea6c-115">Requirements</span></span>  
 <span data-ttu-id="1ea6c-116">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="1ea6c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea6c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ea6c-117">See also</span></span>
- [<span data-ttu-id="1ea6c-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="1ea6c-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1ea6c-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="1ea6c-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1ea6c-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="1ea6c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
