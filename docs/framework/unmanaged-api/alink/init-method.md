---
title: Metodo Init
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf96770dd58c9b84596c082a615f626ec723cc6c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787242"
---
# <a name="init-method"></a><span data-ttu-id="c41e1-102">Metodo Init</span><span class="sxs-lookup"><span data-stu-id="c41e1-102">Init Method</span></span>
<span data-ttu-id="c41e1-103">Prepara gli oggetti che implementano l' [Interfaccia IALink](ialink-interface.md) per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c41e1-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c41e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c41e1-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c41e1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c41e1-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="c41e1-106">Puntatore all' [interfaccia IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) per il dispenser di metadati.</span><span class="sxs-lookup"><span data-stu-id="c41e1-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="c41e1-107">Puntatore all' [interfaccia IMetaDataError](../metadata/imetadataerror-interface.md) a un'interfaccia di gestione degli errori facoltativa.</span><span class="sxs-lookup"><span data-stu-id="c41e1-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c41e1-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c41e1-108">Return Value</span></span>  
 <span data-ttu-id="c41e1-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c41e1-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c41e1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c41e1-110">Requirements</span></span>  
 <span data-ttu-id="c41e1-111">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="c41e1-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41e1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c41e1-112">See also</span></span>

- [<span data-ttu-id="c41e1-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c41e1-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c41e1-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c41e1-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c41e1-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="c41e1-115">ALink API</span></span>](index.md)
