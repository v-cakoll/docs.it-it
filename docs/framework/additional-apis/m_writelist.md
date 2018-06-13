---
title: Campo Connection.m_WriteList
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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d145f6fd21989ada49a581ebf2694dcd56d94351
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743160"
---
# <a name="connectionmwritelist-field"></a>Connection.m\_WriteList campo

`Connection.m_WriteList` è un <xref:System.Collections.ArrayList> di <xref:System.Net.HttpWebRequest> gli oggetti che sono in attesa di essere inviato tramite HTTP.

## <a name="syntax"></a>Sintassi
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> Il `Connection.m_WriteList` campo è privato e non ha significato essere utilizzato direttamente nel codice.
> 
> Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Namespace:** <xref:System.Net>

**Assembly:** System (System. dll)

**Versioni di .NET framework:** disponibile dalla 2.0.
