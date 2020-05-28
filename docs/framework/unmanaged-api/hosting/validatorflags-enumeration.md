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
ms.openlocfilehash: d5eb225241f597baf7a0a5584f4aaf8bf8411ea2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009470"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="ebb54-102">Enumerazione ValidatorFlags</span><span class="sxs-lookup"><span data-stu-id="ebb54-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="ebb54-103">Contiene valori che indicano il tipo di convalida da eseguire in una chiamata al metodo [ICLRValidator:: Validate](iclrvalidator-validate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ebb54-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb54-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebb54-104">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="ebb54-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ebb54-105">Members</span></span>  
  
|<span data-ttu-id="ebb54-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ebb54-106">Member</span></span>|<span data-ttu-id="ebb54-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ebb54-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="ebb54-108">Specifica che deve essere convalidato solo il codice MSIL (Microsoft Intermediate Language) nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="ebb54-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="ebb54-109">Specifica che deve essere convalidato solo il formato del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="ebb54-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="ebb54-110">Specifica che tutti i tipi di convalida devono essere eseguiti e segnalati in.</span><span class="sxs-lookup"><span data-stu-id="ebb54-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="ebb54-111">Specifica che il formato del file eseguibile non deve essere convalidato.</span><span class="sxs-lookup"><span data-stu-id="ebb54-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="ebb54-112">Specifica che i messaggi di errore di convalida devono includere le righe del codice sorgente che generano errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="ebb54-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="ebb54-113">Il valore di questo campo non è valido nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="ebb54-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebb54-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ebb54-114">Requirements</span></span>  
 <span data-ttu-id="ebb54-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebb54-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebb54-116">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="ebb54-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="ebb54-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ebb54-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebb54-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebb54-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb54-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebb54-119">See also</span></span>

- [<span data-ttu-id="ebb54-120">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="ebb54-120">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="ebb54-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="ebb54-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
