---
title: Campo Connection. m_WriteList
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9760e301e25bc6e69ab22b563894cb079a8d58bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120023"
---
# <a name="connectionm_writelist-field"></a><span data-ttu-id="f7c34-102">Connection. m\_campo di writeback</span><span class="sxs-lookup"><span data-stu-id="f7c34-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="f7c34-103">`Connection.m_WriteList` è un <xref:System.Collections.ArrayList> di oggetti <xref:System.Net.HttpWebRequest> accodati per essere inviati tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="f7c34-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="f7c34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7c34-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="f7c34-105">Il campo `Connection.m_WriteList` è privato e non è destinato a essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="f7c34-105">The `Connection.m_WriteList` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="f7c34-106">Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="f7c34-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f7c34-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7c34-107">Requirements</span></span>

<span data-ttu-id="f7c34-108">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f7c34-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f7c34-109">**Assembly:** System (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="f7c34-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f7c34-110">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="f7c34-110">**.NET Framework versions:** Available since 2.0.</span></span>
