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
ms.openlocfilehash: 3c8864aa604b0483130eac5aa0d7c0640abbac99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443723"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="8f9a4-102">Enumerazione CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="8f9a4-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="8f9a4-103">Contiene valori che descrivono il tipo di mapping del file restituito da una chiamata al [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f9a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f9a4-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="8f9a4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8f9a4-105">Members</span></span>  
  
|<span data-ttu-id="8f9a4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8f9a4-106">Member</span></span>|<span data-ttu-id="8f9a4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f9a4-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="8f9a4-108">Il file viene eseguito il mapping come file di dati.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-108">The file is mapped as a data file.</span></span> <span data-ttu-id="8f9a4-109">Vale a dire il `SEC_IMAGE` flag non è stato passato a Microsoft Win32 `CreateFileMapping` (funzione).</span><span class="sxs-lookup"><span data-stu-id="8f9a4-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="8f9a4-110">Il file viene eseguito il mapping per l'esecuzione, utilizzando il `LoadLibrary` funzione o `CreateFileMapping` utilizzabile con il `SEC_IMAGE` flag.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f9a4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f9a4-111">Requirements</span></span>  
 <span data-ttu-id="8f9a4-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f9a4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f9a4-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="8f9a4-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8f9a4-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f9a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9a4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f9a4-115">See Also</span></span>  
 [<span data-ttu-id="8f9a4-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="8f9a4-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="8f9a4-117">Metodo GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="8f9a4-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
