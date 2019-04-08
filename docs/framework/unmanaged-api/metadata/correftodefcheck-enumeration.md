---
title: Enumerazione CorRefToDefCheck
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82abeb0ce3db075d794787bb1fcd5bc18321bef2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093891"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="c8dde-102">Enumerazione CorRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="c8dde-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="c8dde-103">Specifica i flag per controllare quali elementi a cui viene fatto riferimento vengono convertiti nelle relative definizioni per ottimizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="c8dde-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8dde-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8dde-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="c8dde-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c8dde-105">Members</span></span>  
  
|<span data-ttu-id="c8dde-106">Member</span><span class="sxs-lookup"><span data-stu-id="c8dde-106">Member</span></span>|<span data-ttu-id="c8dde-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8dde-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="c8dde-108">Specifica che i riferimenti di tipo e membro devono essere convertiti alle definizioni.</span><span class="sxs-lookup"><span data-stu-id="c8dde-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="c8dde-109">Questo è il valore predefinito (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="c8dde-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="c8dde-110">Specifica che tutti gli elementi di cui viene fatto riferimento devono essere convertiti alle definizioni.</span><span class="sxs-lookup"><span data-stu-id="c8dde-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="c8dde-111">Specifica che nessun elemento di cui viene fatto riferimento deve essere convertito alle definizioni.</span><span class="sxs-lookup"><span data-stu-id="c8dde-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="c8dde-112">Specifica che solo i riferimenti di tipo devono essere convertiti per le definizioni dei tipi.</span><span class="sxs-lookup"><span data-stu-id="c8dde-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="c8dde-113">Specifica che solo i riferimenti a membri devono essere convertiti alle definizioni.</span><span class="sxs-lookup"><span data-stu-id="c8dde-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="c8dde-114">Riferimenti ai membri, devono essere convertiti in definizioni di metodo o definizioni di campo.</span><span class="sxs-lookup"><span data-stu-id="c8dde-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8dde-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8dde-115">Requirements</span></span>  
 <span data-ttu-id="c8dde-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8dde-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8dde-117">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="c8dde-117">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="c8dde-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c8dde-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8dde-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8dde-119">See also</span></span>

- [<span data-ttu-id="c8dde-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="c8dde-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
