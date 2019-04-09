---
title: Enumerazione ValidatorFlags
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa10ae1cf67339a6719210f3162f19ac648e8ee5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127413"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="e0098-102">Enumerazione ValidatorFlags</span><span class="sxs-lookup"><span data-stu-id="e0098-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="e0098-103">Contiene valori che indicano il tipo di convalida che deve essere eseguita in una chiamata per il [ICLRValidator](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="e0098-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0098-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0098-104">Syntax</span></span>  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="e0098-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e0098-105">Members</span></span>  
  
|<span data-ttu-id="e0098-106">Member</span><span class="sxs-lookup"><span data-stu-id="e0098-106">Member</span></span>|<span data-ttu-id="e0098-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0098-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="e0098-108">Specifica che solo il Microsoft intermediate language (MSIL) nel file eseguibile deve essere convalidato.</span><span class="sxs-lookup"><span data-stu-id="e0098-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="e0098-109">Specifica che solo il formato del file eseguibile deve essere convalidato.</span><span class="sxs-lookup"><span data-stu-id="e0098-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="e0098-110">Specifica che tutti i tipi di convalida devono essere eseguiti e segnalati in.</span><span class="sxs-lookup"><span data-stu-id="e0098-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="e0098-111">Specifica che il formato del file eseguibile non deve essere convalidato.</span><span class="sxs-lookup"><span data-stu-id="e0098-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="e0098-112">Specifica che i messaggi di errore di convalida devono includere le righe di codice sorgente che generano errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="e0098-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="e0098-113">Questo valore del campo non è valido in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="e0098-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0098-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0098-114">Requirements</span></span>  
 <span data-ttu-id="e0098-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0098-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0098-116">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="e0098-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="e0098-117">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0098-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e0098-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e0098-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0098-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0098-119">See also</span></span>

- [<span data-ttu-id="e0098-120">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="e0098-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="e0098-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="e0098-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
