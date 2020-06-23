---
title: ConnectionGroup. m_ConnectionList campo
description: Informazioni sul campo ConnectionGroup. m_ConnectionList in .NET, che contiene gli oggetti connessione che servono lo stesso URI e condividono i valori per altre proprietà.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
ms.openlocfilehash: 478b2441c062e8df6f4e718bd66d7af329f20f12
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989731"
---
# <a name="connectiongroupm_connectionlist-field"></a><span data-ttu-id="d1f8f-103">Campo di connessione ConnectionGroup. m \_</span><span class="sxs-lookup"><span data-stu-id="d1f8f-103">ConnectionGroup.m\_ConnectionList Field</span></span>

<span data-ttu-id="d1f8f-104">`ConnectionGroup.m_ConnectionList`è un oggetto <xref:System.Collections.ArrayList> di oggetti Connection che serve lo stesso URI e condividono gli stessi valori per altre proprietà, ad esempio la scadenza e l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d1f8f-104">`ConnectionGroup.m_ConnectionList` is an <xref:System.Collections.ArrayList> of connection objects that serves the same URI and share the same values for some other properties like expiration and authentication.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1f8f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1f8f-105">Syntax</span></span>
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> <span data-ttu-id="d1f8f-106">Il `ConnectionGroup.m_ConnectionList` campo è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="d1f8f-106">The `ConnectionGroup.m_ConnectionList` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d1f8f-107">Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="d1f8f-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1f8f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1f8f-108">Requirements</span></span>

<span data-ttu-id="d1f8f-109">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d1f8f-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d1f8f-110">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="d1f8f-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d1f8f-111">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="d1f8f-111">**.NET Framework versions:** Available since 2.0.</span></span>
