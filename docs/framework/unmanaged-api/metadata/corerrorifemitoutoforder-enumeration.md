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
ms.openlocfilehash: 16f6d7bf6fa1730d50cfe81526817e492a453dad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781977"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="ed7a4-102">Enumerazione CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="ed7a4-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="ed7a4-103">Contiene valori di flag che indicano in quali condizioni è necessario generare un messaggio di errore per notificare che i metadati sono stati emessi senza ordine.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed7a4-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="ed7a4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ed7a4-105">Members</span></span>  
  
|<span data-ttu-id="ed7a4-106">Member</span><span class="sxs-lookup"><span data-stu-id="ed7a4-106">Member</span></span>|<span data-ttu-id="ed7a4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed7a4-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="ed7a4-108">Indica il comportamento predefinito, che non genera messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="ed7a4-109">Indica che il compilatore non deve generare i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="ed7a4-110">Indica che il compilatore deve generare un messaggio di errore quando un campo, proprietà, eventi, metodo o parametro viene generato nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="ed7a4-111">Indica che il compilatore deve generare un messaggio di errore quando un metodo viene generato nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="ed7a4-112">Indica che il compilatore deve generare un messaggio di errore quando un campo viene generato nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="ed7a4-113">Indica che il compilatore deve generare un messaggio di errore quando un parametro viene generato nell'ordine errato.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="ed7a4-114">Indica che il compilatore deve generare un messaggio di errore quando una proprietà viene emessa fuori sequenza.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="ed7a4-115">Indica che il compilatore deve generare un messaggio di errore quando viene generato un evento non in ordine.</span><span class="sxs-lookup"><span data-stu-id="ed7a4-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed7a4-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed7a4-116">Requirements</span></span>  
 <span data-ttu-id="ed7a4-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed7a4-118">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="ed7a4-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ed7a4-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed7a4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7a4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed7a4-120">See also</span></span>

- [<span data-ttu-id="ed7a4-121">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ed7a4-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
