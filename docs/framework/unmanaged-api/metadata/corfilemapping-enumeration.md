---
title: Enumerazione CorFileMapping
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3056836d289383161f9fa538c3c6349f88b6ba6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175617"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="dfdef-102">Enumerazione CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="dfdef-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="dfdef-103">Contiene valori che descrivono il tipo di mapping di file che viene restituito da una chiamata per il [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="dfdef-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfdef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfdef-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="dfdef-105">Membri</span><span class="sxs-lookup"><span data-stu-id="dfdef-105">Members</span></span>  
  
|<span data-ttu-id="dfdef-106">Member</span><span class="sxs-lookup"><span data-stu-id="dfdef-106">Member</span></span>|<span data-ttu-id="dfdef-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfdef-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="dfdef-108">Il file viene mappato come un file di dati.</span><span class="sxs-lookup"><span data-stu-id="dfdef-108">The file is mapped as a data file.</span></span> <span data-ttu-id="dfdef-109">Vale a dire il `SEC_IMAGE` flag non è stato passato a Microsoft Win32 `CreateFileMapping` (funzione).</span><span class="sxs-lookup"><span data-stu-id="dfdef-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="dfdef-110">Il file viene eseguito il mapping per l'esecuzione, usando il `LoadLibrary` (funzione) o il `CreateFileMapping` utilizzabile con il `SEC_IMAGE` flag.</span><span class="sxs-lookup"><span data-stu-id="dfdef-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfdef-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfdef-111">Requirements</span></span>  
 <span data-ttu-id="dfdef-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfdef-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfdef-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="dfdef-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="dfdef-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dfdef-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dfdef-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfdef-115">See also</span></span>

- [<span data-ttu-id="dfdef-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="dfdef-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="dfdef-117">Metodo GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="dfdef-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
