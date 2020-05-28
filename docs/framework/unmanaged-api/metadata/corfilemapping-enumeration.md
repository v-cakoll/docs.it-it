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
ms.openlocfilehash: 0ed1579886f1682348a136be3391f6bdc2543d26
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007390"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="71678-102">Enumerazione CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="71678-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="71678-103">Contiene valori che descrivono il tipo di mapping di file restituito da una chiamata al metodo [IMetaDataInfo:: GetFileMapping](imetadatainfo-getfilemapping-method.md) .</span><span class="sxs-lookup"><span data-stu-id="71678-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71678-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71678-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="71678-105">Membri</span><span class="sxs-lookup"><span data-stu-id="71678-105">Members</span></span>  
  
|<span data-ttu-id="71678-106">Membro</span><span class="sxs-lookup"><span data-stu-id="71678-106">Member</span></span>|<span data-ttu-id="71678-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71678-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="71678-108">Il file viene mappato come file di dati.</span><span class="sxs-lookup"><span data-stu-id="71678-108">The file is mapped as a data file.</span></span> <span data-ttu-id="71678-109">Ovvero, il `SEC_IMAGE` flag non è stato passato alla funzione Microsoft Win32 `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="71678-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="71678-110">È stato eseguito il mapping del file per l'esecuzione, usando la `LoadLibrary` funzione o la `CreateFileMapping` funzione con il `SEC_IMAGE` flag.</span><span class="sxs-lookup"><span data-stu-id="71678-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71678-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71678-111">Requirements</span></span>  
 <span data-ttu-id="71678-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71678-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71678-113">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="71678-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="71678-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71678-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71678-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71678-115">See also</span></span>

- [<span data-ttu-id="71678-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="71678-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="71678-117">Metodo GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="71678-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)
