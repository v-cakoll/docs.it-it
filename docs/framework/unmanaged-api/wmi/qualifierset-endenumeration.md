---
title: QualifierSet_EndEnumeration function (Unmanaged API Reference)
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
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176747"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="4b79f-103">Funzione QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="4b79f-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="4b79f-104">Termina l'enumerazione iniziata con una chiamata alla funzione [QualifierSet_BeginEnumeration.](qualifierset-beginenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="4b79f-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4b79f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b79f-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="4b79f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b79f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4b79f-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="4b79f-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="4b79f-108">`ptr`[in] Puntatore a [un'istanza di IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="4b79f-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="4b79f-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4b79f-109">Return value</span></span>

<span data-ttu-id="4b79f-110">Il seguente valore restituito da questa funzione è definito nel file di intestazione WbemCli.h oppure è possibile definirlo come costante nel codice:The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span><span class="sxs-lookup"><span data-stu-id="4b79f-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="4b79f-111">Costante</span><span class="sxs-lookup"><span data-stu-id="4b79f-111">Constant</span></span>  |<span data-ttu-id="4b79f-112">valore</span><span class="sxs-lookup"><span data-stu-id="4b79f-112">Value</span></span>  |<span data-ttu-id="4b79f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b79f-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4b79f-114">0</span><span class="sxs-lookup"><span data-stu-id="4b79f-114">0</span></span> | <span data-ttu-id="4b79f-115">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4b79f-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4b79f-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4b79f-116">Remarks</span></span>

<span data-ttu-id="4b79f-117">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .</span><span class="sxs-lookup"><span data-stu-id="4b79f-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="4b79f-118">Questa chiamata è consigliata, ma non obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="4b79f-118">This call is recommended, but not required.</span></span> <span data-ttu-id="4b79f-119">Rilascia immediatamente le risorse associate all'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4b79f-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="4b79f-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b79f-120">Requirements</span></span>  

<span data-ttu-id="4b79f-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b79f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="4b79f-122">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4b79f-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="4b79f-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4b79f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b79f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b79f-124">See also</span></span>

- [<span data-ttu-id="4b79f-125">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="4b79f-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
