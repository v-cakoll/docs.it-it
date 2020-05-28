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
ms.openlocfilehash: ce6f5993b9c1aeb63e121b3567ee468cea1c9318
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007520"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="1c604-102">Enumerazione CorRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="1c604-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="1c604-103">Specifica i flag per controllare quali elementi a cui viene fatto riferimento vengono convertiti nelle relative definizioni per ottimizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="1c604-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c604-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c604-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="1c604-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1c604-105">Members</span></span>  
  
|<span data-ttu-id="1c604-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1c604-106">Member</span></span>|<span data-ttu-id="1c604-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c604-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="1c604-108">Specifica che i riferimenti ai tipi e i riferimenti ai membri devono essere convertiti in definizioni.</span><span class="sxs-lookup"><span data-stu-id="1c604-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="1c604-109">Si tratta del valore predefinito ( `MDTypeRefToDef` &#124; `MDMemberRefToDef` ).</span><span class="sxs-lookup"><span data-stu-id="1c604-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="1c604-110">Specifica che tutti gli elementi a cui si fa riferimento devono essere convertiti in definizioni.</span><span class="sxs-lookup"><span data-stu-id="1c604-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="1c604-111">Specifica che nessun elemento a cui si fa riferimento deve essere convertito nelle definizioni.</span><span class="sxs-lookup"><span data-stu-id="1c604-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="1c604-112">Specifica che solo i riferimenti ai tipi devono essere convertiti nelle definizioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="1c604-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="1c604-113">Specifica che solo i riferimenti ai membri devono essere convertiti in definizioni.</span><span class="sxs-lookup"><span data-stu-id="1c604-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="1c604-114">Ovvero i riferimenti ai membri devono essere convertiti in definizioni di metodo o definizioni di campo.</span><span class="sxs-lookup"><span data-stu-id="1c604-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c604-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c604-115">Requirements</span></span>  
 <span data-ttu-id="1c604-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c604-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c604-117">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="1c604-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1c604-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c604-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c604-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c604-119">See also</span></span>

- [<span data-ttu-id="1c604-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="1c604-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
