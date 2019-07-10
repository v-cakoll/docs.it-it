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
ms.openlocfilehash: 2ae87dd4538a9a8e88591f498c0ce77b51bfa852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781613"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="07fd9-102">Enumerazione CorRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="07fd9-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="07fd9-103">Specifica i flag per controllare quali elementi a cui viene fatto riferimento vengono convertiti nelle relative definizioni per ottimizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="07fd9-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07fd9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07fd9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="07fd9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="07fd9-105">Members</span></span>  
  
|<span data-ttu-id="07fd9-106">Member</span><span class="sxs-lookup"><span data-stu-id="07fd9-106">Member</span></span>|<span data-ttu-id="07fd9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07fd9-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="07fd9-108">Specifica che i riferimenti di tipo e membro devono essere convertiti alle definizioni.</span><span class="sxs-lookup"><span data-stu-id="07fd9-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="07fd9-109">Questo è il valore predefinito (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="07fd9-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="07fd9-110">Specifica che tutti gli elementi di cui viene fatto riferimento devono essere convertiti alle definizioni.</span><span class="sxs-lookup"><span data-stu-id="07fd9-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="07fd9-111">Specifica che nessun elemento di cui viene fatto riferimento deve essere convertito alle definizioni.</span><span class="sxs-lookup"><span data-stu-id="07fd9-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="07fd9-112">Specifica che solo i riferimenti di tipo devono essere convertiti per le definizioni dei tipi.</span><span class="sxs-lookup"><span data-stu-id="07fd9-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="07fd9-113">Specifica che solo i riferimenti a membri devono essere convertiti alle definizioni.</span><span class="sxs-lookup"><span data-stu-id="07fd9-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="07fd9-114">Riferimenti ai membri, devono essere convertiti in definizioni di metodo o definizioni di campo.</span><span class="sxs-lookup"><span data-stu-id="07fd9-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07fd9-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07fd9-115">Requirements</span></span>  
 <span data-ttu-id="07fd9-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07fd9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07fd9-117">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="07fd9-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="07fd9-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07fd9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07fd9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07fd9-119">See also</span></span>

- [<span data-ttu-id="07fd9-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="07fd9-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
