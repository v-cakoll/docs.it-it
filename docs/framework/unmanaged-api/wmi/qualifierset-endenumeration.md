---
title: Funzione QualifierSet_EndEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_EndEnumeration termina un'enumerazione.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5a817174ec4c4e4407c19bb1d6d2d852d86dd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798326"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="89a92-103">QualifierSet_EndEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="89a92-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="89a92-104">Termina l'enumerazione iniziata con una chiamata alla funzione [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="89a92-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="89a92-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89a92-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="89a92-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="89a92-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="89a92-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="89a92-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="89a92-108">in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="89a92-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="89a92-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="89a92-109">Return value</span></span>

<span data-ttu-id="89a92-110">Il valore seguente restituito da questa funzione è definito nel file di intestazione *WbemCli. h* oppure è possibile definirlo come costante nel codice:</span><span class="sxs-lookup"><span data-stu-id="89a92-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="89a92-111">Costante</span><span class="sxs-lookup"><span data-stu-id="89a92-111">Constant</span></span>  |<span data-ttu-id="89a92-112">Valore</span><span class="sxs-lookup"><span data-stu-id="89a92-112">Value</span></span>  |<span data-ttu-id="89a92-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89a92-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="89a92-114">0</span><span class="sxs-lookup"><span data-stu-id="89a92-114">0</span></span> | <span data-ttu-id="89a92-115">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="89a92-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="89a92-116">Note</span><span class="sxs-lookup"><span data-stu-id="89a92-116">Remarks</span></span>

<span data-ttu-id="89a92-117">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .</span><span class="sxs-lookup"><span data-stu-id="89a92-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="89a92-118">Questa chiamata è consigliata, ma non obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="89a92-118">This call is recommended, but not required.</span></span> <span data-ttu-id="89a92-119">Rilascia immediatamente le risorse associate all'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="89a92-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="89a92-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89a92-120">Requirements</span></span>  

<span data-ttu-id="89a92-121">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89a92-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="89a92-122">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="89a92-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="89a92-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="89a92-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a92-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89a92-124">See also</span></span>

- [<span data-ttu-id="89a92-125">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="89a92-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
