---
title: ServicePointManager. s_ServicePointTable campo
description: Leggere le informazioni sul campo ServicePointManager. s_ServicePointTable in .NET. Questo campo della tabella hash contiene le connessioni HTTP attive (ServicePoints) in AppDomain.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989537"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>Campo ServicePointTable di ServicePointManager. s \_

`ServicePointManager.s_ServicePointTable`è un oggetto <xref:System.Collections.Hashtable> che contiene l'elenco di connessioni HTTP attive <xref:System.Net.ServicePoint> nell'oggetto <xref:System.AppDomain> .

## <a name="syntax"></a>Sintassi
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> Il `ServicePointManager.s_ServicePointTable` campo è privato e non è destinato a essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo campo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
