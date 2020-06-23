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
# <a name="connectiongroupm_connectionlist-field"></a>Campo di connessione ConnectionGroup. m \_

`ConnectionGroup.m_ConnectionList`è un oggetto <xref:System.Collections.ArrayList> di oggetti Connection che serve lo stesso URI e condividono gli stessi valori per altre proprietà, ad esempio la scadenza e l'autenticazione.

## <a name="syntax"></a>Sintassi
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> Il `ConnectionGroup.m_ConnectionList` campo è privato e non è destinato a essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
