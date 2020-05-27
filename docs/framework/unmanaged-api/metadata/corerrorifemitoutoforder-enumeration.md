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
ms.openlocfilehash: fec049297bfa12d86cb2a7f7950e84ae540832b1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007433"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="73506-102">Enumerazione CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="73506-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="73506-103">Contiene valori di flag che indicano in quali condizioni è necessario generare un messaggio di errore per notificare che i metadati sono stati emessi senza ordine.</span><span class="sxs-lookup"><span data-stu-id="73506-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73506-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73506-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="73506-105">Membri</span><span class="sxs-lookup"><span data-stu-id="73506-105">Members</span></span>  
  
|<span data-ttu-id="73506-106">Membro</span><span class="sxs-lookup"><span data-stu-id="73506-106">Member</span></span>|<span data-ttu-id="73506-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73506-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="73506-108">Indica il comportamento predefinito, che non genera messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="73506-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="73506-109">Indica che il compilatore non deve generare messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="73506-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="73506-110">Indica che il compilatore deve generare un messaggio di errore quando un campo, una proprietà, un evento, un metodo o un parametro viene emesso fuori ordine.</span><span class="sxs-lookup"><span data-stu-id="73506-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="73506-111">Indica che il compilatore deve generare un messaggio di errore quando viene emesso un metodo non ordinato.</span><span class="sxs-lookup"><span data-stu-id="73506-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="73506-112">Indica che il compilatore deve generare un messaggio di errore quando un campo viene emesso senza ordine.</span><span class="sxs-lookup"><span data-stu-id="73506-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="73506-113">Indica che il compilatore deve generare un messaggio di errore quando un parametro viene emesso fuori ordine.</span><span class="sxs-lookup"><span data-stu-id="73506-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="73506-114">Indica che il compilatore deve generare un messaggio di errore quando una proprietà viene emessa senza ordine.</span><span class="sxs-lookup"><span data-stu-id="73506-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="73506-115">Indica che il compilatore deve generare un messaggio di errore quando viene generato un evento non ordinato.</span><span class="sxs-lookup"><span data-stu-id="73506-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73506-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73506-116">Requirements</span></span>  
 <span data-ttu-id="73506-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73506-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73506-118">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="73506-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="73506-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73506-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73506-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73506-120">See also</span></span>

- [<span data-ttu-id="73506-121">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="73506-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
