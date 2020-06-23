---
title: Classe comnetos (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990400"
---
# <a name="comnetos-class"></a>Classe ComNetOS

Fornisce informazioni sul sistema operativo corrente, ad esempio la versione e il tipo di installazione (client o server). Questa classe non può essere ereditata.
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> Questa classe è interna e non è destinata all'uso diretto nel codice.
>
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="iswin7orlater-field"></a>Campo IsWin7orLater

Specifica se la versione del sistema operativo è Windows 7 o versioni successive.

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)
