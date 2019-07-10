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
ms.openlocfilehash: 719f0522cc43625a4d6cc8afa838d869e47b40d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781845"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="ecaa5-102">Enumerazione CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="ecaa5-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="ecaa5-103">Contiene valori che descrivono il tipo di mapping di file che viene restituito da una chiamata per il [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ecaa5-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecaa5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecaa5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="ecaa5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ecaa5-105">Members</span></span>  
  
|<span data-ttu-id="ecaa5-106">Member</span><span class="sxs-lookup"><span data-stu-id="ecaa5-106">Member</span></span>|<span data-ttu-id="ecaa5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecaa5-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="ecaa5-108">Il file viene mappato come un file di dati.</span><span class="sxs-lookup"><span data-stu-id="ecaa5-108">The file is mapped as a data file.</span></span> <span data-ttu-id="ecaa5-109">Vale a dire il `SEC_IMAGE` flag non è stato passato a Microsoft Win32 `CreateFileMapping` (funzione).</span><span class="sxs-lookup"><span data-stu-id="ecaa5-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="ecaa5-110">Il file viene eseguito il mapping per l'esecuzione, usando il `LoadLibrary` (funzione) o il `CreateFileMapping` utilizzabile con il `SEC_IMAGE` flag.</span><span class="sxs-lookup"><span data-stu-id="ecaa5-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ecaa5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ecaa5-111">Requirements</span></span>  
 <span data-ttu-id="ecaa5-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecaa5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecaa5-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="ecaa5-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ecaa5-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecaa5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecaa5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecaa5-115">See also</span></span>

- [<span data-ttu-id="ecaa5-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ecaa5-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="ecaa5-117">Metodo GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="ecaa5-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
