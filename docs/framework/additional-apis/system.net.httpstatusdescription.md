---
title: Classe HttpStatusDescription (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990393"
---
# <a name="httpstatusdescription-class"></a>Classe HttpStatusDescription

Fornisce descrizioni dello stato HTTP standard. Questa classe non può essere ereditata.

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> Questa classe è interna e non è destinata all'uso diretto nel codice.
>
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="get-method"></a>metodo Get

Restituisce la descrizione associata al codice di stato HTTP specificato.

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a>Parametri

`code` <xref:System.Int32>

Codice di stato HTTP, ad esempio `404` .

### <a name="return-value"></a>Valore restituito

<xref:System.String?displayProperty=nameWithType>

Descrizione dello stato HTTP.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)
