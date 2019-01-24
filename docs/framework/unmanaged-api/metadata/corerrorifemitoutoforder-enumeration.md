---
title: Enumerazione CorErrorIfEmitOutOfOrder
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 084f0bbab130cd4e7334184fe9baa322c0487942
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616771"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="ccae1-102">Enumerazione CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="ccae1-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="ccae1-103">Contiene valori di flag che indicano in quali condizioni è necessario generare un messaggio di errore per notificare che i metadati sono stati emessi senza ordine.</span><span class="sxs-lookup"><span data-stu-id="ccae1-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccae1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccae1-104">Syntax</span></span>  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="ccae1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ccae1-105">Members</span></span>  
  
|<span data-ttu-id="ccae1-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ccae1-106">Member</span></span>|<span data-ttu-id="ccae1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccae1-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="ccae1-108">Indica il comportamento predefinito, che non genera messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="ccae1-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="ccae1-109">Indica che il compilatore non deve generare i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="ccae1-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="ccae1-110">Indica che il compilatore deve generare un messaggio di errore quando un campo, proprietà, eventi, metodo o parametro viene generato nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="ccae1-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="ccae1-111">Indica che il compilatore deve generare un messaggio di errore quando un metodo viene generato nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="ccae1-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="ccae1-112">Indica che il compilatore deve generare un messaggio di errore quando un campo viene generato nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="ccae1-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="ccae1-113">Indica che il compilatore deve generare un messaggio di errore quando un parametro viene generato nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="ccae1-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="ccae1-114">Indica che il compilatore deve generare un messaggio di errore quando una proprietà viene emessa fuori sequenza.</span><span class="sxs-lookup"><span data-stu-id="ccae1-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="ccae1-115">Indica che il compilatore deve generare un messaggio di errore quando viene generato un evento non in ordine.</span><span class="sxs-lookup"><span data-stu-id="ccae1-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccae1-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ccae1-116">Requirements</span></span>  
 <span data-ttu-id="ccae1-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccae1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccae1-118">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="ccae1-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ccae1-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccae1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccae1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccae1-120">See also</span></span>
- [<span data-ttu-id="ccae1-121">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ccae1-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
